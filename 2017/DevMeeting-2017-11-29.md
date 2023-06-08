---
lang: en
tags: Ruby, ruby-dev-meeting
---

# DevMeeting-2017-11-29

Date: 2017/11/29 (Mon)
Time: 14:00- 18:00 (JST)
Place: MoneyForward, Inc.
Sign-up: https://ruby.connpass.com/event/70066/
Attendees: (add your name here if you would like to appear)
Regrets: (add your name here if you often attend, but can't attend this time) Martin Dürst
Language: mostly Japanese (sorry for non native Japanese speakers)

Please add your favorite ticket numbers you want to ask to discuss.

* NOTE
  * Dev meeting *IS NOT* a decision making place. All decisions should be done at the bug tracker.
  * Dev meeting is a place we can ask Matz, nobu, nurse and other developers directly. Matz is a very busy person.  Take this opportunity to ask him. If you can not attend, other attendees can ask instead of you (if attendees can understand your issue).
  * We will write a log about discussion to a file or to each ticket in English.
  * All activities are best-effort (keep in mind that most of us are volunteer developers).
  * The date, time and place is scheduled according to when/where we can reserve Matz's time.

# Agenda

* NOTE: Write at least "ticket number/title/link" and your name (see example below). Explain details on the ticket. If you cannot attend the meeting, we appreciate a short summary because we can understand it more easily (long discussion is difficult to read, especially in a non-native language). Your motivation is also welcome.

## About 2.5 timeframe

* https://bugs.ruby-lang.org/projects/ruby-trunk/wiki/ReleaseEngineering25

## Carry-over from previous meeting(s)

- bugs that are not assigned (shyouhei)
    * [Bug #13675]&nbsp;Should Zlib::GzipReader#ungetc accept nil?
    * [Bug #13700]&nbsp;Enumerable#sum may not work for Ranges subclasses due to optimization (**mrkn**)
    * [Bug #13716]&nbsp;Unexpected or undocumented (or maybe both) behaviour when mixing String#scan with named captures
    * [Bug #13549]&nbsp;MinGW / Windows encoding - Two issues
    * [Bug #13746]&nbsp;windows-pr gemのRuby　2.4 32bit版でのSEGV
    * [Bug #13768]&nbsp;SIGCHLD and Thread dead-lock problem
    * [Bug #13773]&nbsp;Improve String#prepend performance if only one argument is given
    * [Bug #13774]&nbsp;for methods defined from procs, the binding of the resulting bound method proc does not have access to the original proc's closure environment
    * [Bug #13781]&nbsp;Should the safe navigation operator invoke `nil?`
    * [Bug #13795]&nbsp;Hash#select return type does not match Hash#find_all
    * [Bug #13811]&nbsp;Ruby 2.4.1 fails to compile inside qemu armhf - signal 11 (Segmentation fault)
    * [Bug #13818]&nbsp;Licence issue with use of Onigmo rather than Oniguruma library files
    * [Bug #13827]&nbsp;Improve performance of `Base64.urlsafe_encode64`
    * [Bug #13835]&nbsp;Using 'open-uri' with 'tempfile' causes an exception
    * [Bug #13167]&nbsp;Dir.glob is 25x slower since Ruby 2.2
    * [Bug #12036]&nbsp;Enumerator's automatic rewind behavior
    * [Bug #13848]&nbsp;BigDecimal.new('200.') raises an exception
    * [Bug #13880]&nbsp;`BigDecimal(string)` should raise on invalid values in `string`
    * [Bug #13876]&nbsp;Tempfile's finalizer can be interrupted by a Timeout exception which can cause the process to hang
    * [Bug #13885]&nbsp;Random.urandom と securerandom について
    * [Bug #10104]&nbsp;Fileutils cp_r fails on sockets or fifes even if File.mknod and File.mkfifo are defined
    * [Bug #13930]&nbsp;Exception is caught in rescue above ensure
    * [Bug #13970]&nbsp;Base64 urlsafe_decode64 unsafe use of tr.
    * [Bug #14010]&nbsp;RubyVM logic in forwardable backported to 2.3, not removed
    * [Bug #14016]&nbsp;URI IPv6 address can't be used to open socket
    * [Bug #14015]&nbsp;Enumerable & Hash yielding arity
    * [Bug #13887]&nbsp;test/ruby/test_io.rb may get stuck with FIBER_USE_NATIVE=0 on Linux
- [Feature #13381]&nbsp;[PATCH] Expose rb_fstring and its family to C extensions (shyouhei) ko1?
- [Feature #13434]&nbsp;better method definition in C API (shyouhei) ko1?
- [Feature #13713]&nbsp;socketの便利メソッドのdatagramのUNIXSocket用対応 (shyouhei)
- [Feature #13715]&nbsp;[PATCH] avoid garbage from Symbol#to_s in interpolation (shyouhei)
- [Feature #13719]&nbsp;[PATCH] net/http: allow existing socket arg for Net::HTTP.start (shyouhei)
- [Feature #13733]&nbsp;Dump the delegator instead of the delegated object (shyouhei)
- [Feature #13625]&nbsp;BigDecimal short form / shorthand (shyouhei)
* [Bug #12159] Thread::Backtrace::Location#path returns absolute path for files loaded by require_relative (a_matsuda)
- [Feature #13751]&nbsp;Suppert SSHFP resource records in rubysl-resolv (shyouhei)
- [Bug #13752]&nbsp;Can't observe sibling refinements (shyouhei)
- [Feature #13763]&nbsp;Trigger "unused variable warning" for unused variables in parameter lists (shyouhei)
- [Feature #13765]&nbsp;Add Proc#bind (shyouhei)
- [Feature #13767]&nbsp;add something like python's buffer protocol to share memory between different narray like classes (shyouhei)
- [Misc #13804]&nbsp;Protected methods cannot be overridden (shyouhei)
- [Feature #13807]&nbsp;A method to filter the receiver against some condition (shyouhei)
- [Feature #13805]&nbsp;Make refinement scoping to be like that of constants (shyouhei)
- [Feature #12282]&nbsp;Hash#dig! for repeated applications of Hash#fetch (shyouhei)
- [Feature #13820]&nbsp;Add a nill coalescing operator (shyouhei)
- [Feature #13770]&nbsp;Can't create valid Cyrillic-named class/module (shyouhei) status?
- [Feature #13581]&nbsp;Syntax sugar for method reference (shyouhei)
- [Feature #13881]&nbsp;Use getcontext/setcontext on OS X (shyouhei)
- [Feature #13883]&nbsp;Change from gperf 3.0.4 to gperf 3.1 (shyouhei)
- [Feature #13890]&nbsp;Allow a regexp as an argument to 'count', to count more interesting things than single characters (shyouhei)
- [Feature #13245]&nbsp;[PATCH] reject inter-thread TLS modification (shyouhei)
- [Feature #13901]&nbsp;Add branch coverage  (shyouhei)
- [Feature #13922]&nbsp;Consider showing warning messages about same-named aliases - either directly or perhaps via the "did you mean gem" (shyouhei)
- [Feature #13924]&nbsp;Add headings/hints to RubyVM::InstructionSequence#disasm (shyouhei)
- [Feature #8661]&nbsp;Add option to print backstrace in reverse order(stack frames first & error last) (shyouhei) objection appealed.
- [Misc #13968]&nbsp;[Ruby 3.x perhaps] - A (minimal?) static variant of ruby (shyouhei)
- [Feature #13969]&nbsp;Dir#each_child (shyouhei)
- [Feature #12115]&nbsp;Add Symbol#call to allow to_proc shorthand with arguments (shyouhei)
- [Feature #5964]&nbsp;Make Symbols an Alternate Syntax for Strings (shyouhei) seems updated since closed
- [Feature #12533]&nbsp;Refinements: allow modules inclusion, in which the module can call internal methods which it defines.  (shyouhei)
- [Feature #13984]&nbsp;BigDecimal should be immutable/frozen and return itself on #dup (shyouhei)
- [Feature #13936]&nbsp;Make regular expressions debugable (shyouhei)
- [Bug #13986]&nbsp;Integer#fdiv with Complex returns unexpected value (shyouhei)
- [Feature #14022]&nbsp;String#surround (shyouhei)

## From attendees

  * [Bug #8352]&nbsp;URI squeezes a sequence of slashes in merging paths when it shouldn't (knu)
  * [Feature #14123]&nbsp;Kernel#pp by default (mame)
  * [Feature #12275]&nbsp;String unescape (tadd)

The tickets below are old tickets whose status is open or assigned (and mame can somewhat understand)

- matz
  * [Feature #1586]&nbsp;Including a module already present in ancestors should not be ignored
  * [Feature #2080]&nbsp;Proc#to_source, Method#to_source
  * [Feature #2323]&nbsp;"Z".."Z".succが空
  * [Feature #2348]&nbsp;RBTree Should be Added to the Standard Library
  * [Feature #2740]&nbsp;Extend const_missing to pass in the nesting
  * [Feature #3072]&nbsp;Classes Inheriting from Data
  * [Feature #11256]&nbsp;anonymous block forwarding
  * [Feature #3447]&nbsp;argument delegation
  * [Feature #3450]&nbsp;Format Strings with Named Arguments & Hash#default
  * [Feature #3591]&nbsp;Adding Numeric#divisor? (Have working implementation)
  * [Feature #3653]&nbsp;Diferential behaviour of positives and negatives ranges as subindex of string or arrays.
  * [Feature #3916]&nbsp;Add flag to ruby to make warnings fatal.
  * [Feature #4052]&nbsp;File.lutime Patch
  * [Feature #4189]&nbsp;FileUtils#ln_r
- nobu
  * [Feature #836]&nbsp;Patches for StringScanner, adding #size, #captures and #values_at
  * [Feature #2324]&nbsp;Dir instance methods for relative path
  * [Bug #3618]&nbsp;inf-ruby prompt and tab completion
- ko1
  * [Feature #2447]&nbsp;reduce GC pressure by symbol table without String instance
  * [Feature #3187]&nbsp;Allow dynamic Fiber stack size
  * [Feature #3731]&nbsp;Easier Embedding API for Ruby
  * [Feature #3809]&nbsp;allow multiple set_trace_func() calls
  * [Bug #4040]&nbsp;SystemStackError with Hash[*a] for Large _a_
- naruse
  * [Feature #2567]&nbsp;Net::HTTP does not handle encoding correctly
  * [Feature #2631]&nbsp;Allow IO#reopen to take a block
  * [Bug #4173]&nbsp;TestProcess#test_wait_and_sigchild が、たまに失敗する
- mrkn
  * [Feature #3269]&nbsp;BigMath.tan がない
  * [Feature #3270]&nbsp;BigMath.exp が絶対値が大きな引数で遅い
- akr
  * [Feature #3608]&nbsp;Enhancing Pathname#each_child to be lazy
  * [Feature #3848]&nbsp;Using http basic authentication for FTP with Open URI
- knu
  * [Feature #3953]&nbsp;TCPSocket / UDPSocket do not accept IPAddr objects.
- anyone
  * [Bug #3594]&nbsp;URI class doesn't do file URL's properly.
  * [Feature #4017]&nbsp;[PATCH] CSV parsing speedup
  * [Bug #4157]&nbsp;test_pty で、たまに出る Failure

## From non-attendees

Write your name and your interest (what do you want to ask and to whom?) please.
  * [Feature #11816] Fix precedence for &. to a useful level  (marcandre)
  * [Feature #8563] Allow instance variables in method definition (marcandre)
  * [Feature #11286] Allow Enumerable#select(String) (marcandre)
  * [Feature #14132] Make Module#attr_{reader|writer|accessor} public (marcandre)
  * [Feature #14133] Make Module#{define|alias|undef|remove}_method public (marcandre)
  * [Feature #1586] Allow module to be included correctly  (marcandre)
  * Patches for StringScanner, adding #size, #captures and #values_at

# Log

Date: 2017/11/29 (Mon)
Time: 14:00- 18:00 (JST)
Place: MoneyForward, Inc.
Sign-up: https://ruby.connpass.com/event/70066/
log edit: https://docs.google.com/document/d/1XTTzUINO2Fegt-eFgGTY8oGF3uTy5Bz4ZXJdKzyFp34/edit#heading=h.ujsctc6nvlk
log: TBD
Agenda
About 2.5 timeframe
https://bugs.ruby-lang.org/projects/ruby-trunk/wiki/ReleaseEngineering25
preview1 released

