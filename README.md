### UraniumX Isotope CPUminer with multi algo support and YespowerURX!
w/Optimizations with Hugepages... v1.0.4 and up.

You must enable hugepage support in your OS to lock pages in memory or you will not benefit from the optimization!

1. See if Hugepages are available for your system: [LINUX]

> cat /sys/kernel/mm/transparent_hugepage/enabled

> OUTPUT: always [madvise] never

##### NOTE: If [never] is selected... You do not have hugepages on your system!

2. Check the state of THP and the size of each Huge-Page and see your systems Huge-Page total with this command:

> cat /proc/meminfo | grep Huge

3. You can add them on the fly, but hugepages will not be available at system boot!

Be sure to match what is available in your system!

##### LINUX EXAMPLES:
> sudo sysctl -w vm.nr_hugepages=1024

##### NOTE:
See the README in the compressed archive on how to add hugepages at LINUX system boot...
Windows can also lock pages in memory, instructions are in the README!


GitHub: isotope-crypto

BitcoinTalk: isotopecrypto

Twitter: @Isotope_Crypto // AKA: Iso Crypto

Discord: isotope-crypto

UraniumX Discord Invite Link: https://discord.gg/Y4EDCsk


#### CONTENTS:
	BIOS TWEAKS
	CPU CACHE PREFETCHING
	PREFETCH
	THREAD CONFIG
	POWERSAVING
	INSTALL ON WINDOWS 10
	SETTING YOUR HUGEPAGES
	WINDOWS HUGEPAGES
	SETTING YOUR CPU AFFINITY
	CPU AFFINITY CHART


#### BIOS TWEAKS
Hyperthreading
In a dedicated mining rig, disabling hyperthreading in bios can give you a nice boost in performance.

#### CPU CACHE PREFETCHING 
Disabling some of the cpu cache prefetch options in bios can also help, especially "CPU adjacent cacheline prefetch",
since the adjacent cacheline is very unlikely to be needed in a mining workload.

#### PREFETCH
After you have found your optimal config, try flipping ONE thread per cpu to the opposite of the rest, this will pretty
much make that thread the designated victim in a cache-starved situation. That thread might now be slower, but the rest
will be faster, so hopefully you gained a few H/s total.

#### THREAD CONFIG
If your cpu has more cache than you can use with normal threads on all cores, you should run additional normal threads on
one or more secondary hyperthreads. If your cpu does not have hyperthreads, then you will need to run some of the miner
threads in double-mode.

#### POWERSAVING
If your cpu is overheating or you need to use the machine for other things as well and it gets sluggish, then you can
replace a pair of normal miner threads with a single miner thread in double-mode.
This only gets you 80-85% of the hashrate of two normal threads, but it will save power and will free up one core for
other uses.
(But the cache will still be full, so you might want to free up some cache if you want to use the computer while mining.)

#### HUGEPAGE AND CPU AFFINITY
Instructions in the PGP Signed Readme included in the archive!

#### WINDOWS 10 MININUM REQUIREMENTS:
Visual C++ redistributable 2015 X64 [Windows]

Precompiled Windows binaries are built on a Windows host using SYS2 and Mingw

#### INSTALL LINUX DEPENDENCIES FOR UBUNTU 18.04 LINUX

> sudo apt-get install build-essential libssl-dev libcurl4-openssl-dev libjansson-dev libgmp-dev automake zlib1g-dev curl openssl m4

#### INSTALL ON UBUNTU 18.04 LINUX:

Extract UraniumX-Isotope-CPUminer_vx.x.x_linux-x86.[tar.gz or .zip] using an extract utility.

tar -xvzf UraniumX-Isotope-CPUminer_vx.x.x_linux-x86.tar.gz

cd UraniumX-Isotope-CPUminer_vx.x.x_linux-x86

cd native [or other CPU Architecture type folder...]

#### NOTE:
The archive contains all respective binaries for many different CPU types!
Use the native version if you are not sure of the type of CPU instructions of your CPU.

#### INSTALL ON WINDOWS 10 [ Don't have 32 bit programs on the system, it will report an error and not work! ]
Extract UraniumX-Isotope-CPUminer_vx.x.x_Windows-x86_64.zip using an extract utility.

1. Open the "Start.cmd" file shell script within the folder that matches your processor file type.
   NOTE: If you are not sure of your CPU, the native version will be fine and figure it out later! 

2. Choose the correct syntax for the CPU type that you are using.

3. Enter your choice of pool, your UraniumX wallet address or other settings within the syntax line you
   are using or donate to me using the sample syntax provided to test.
   
4. Open up a terminal within the folder of the CPU version you are using and at the prompt enter: ./Start

5. Happy Mining! -Isotope Crypto

#### WINDOWS MINING SYNTAX:
Choose your arch and edit with your choice of pool and wallet address!
Open a cmd terminal and run the following...

#### SYNTAX: [Use the correct named file for the syntax architecture!]
> urx-isotope-cpuminer.exe -a yespowerurx -o stratum+tcp://uranium-x.net:443 -u UjyU6wt51jwUd9bwogoKkPkE6UJCupRhf3 -p c=URX,d=1,donate

#### NOTE: DO NOT HAVE ANY SPACES BETWEEN YOUR OPTIONS!!
[IE:: x,c=URX,d=1,rigname,etc]

urx-isotope-cpuminer.exe is a console program that is executed from a DOS command prompt.
There is no GUI and no mouse support.

Miner programs are often flagged as malware by antivirus programs.
This is a false positive, they are flagged simply because they are cryptocurrency miners.
If you don't trust the software, don't use it.

Choose the exe that best matches you CPU's features or use trial and error to find the fastest one that doesn't crash.
Pay attention to the features listed at cpuminer startup to ensure you are mining at optimum speed using the best available features.

Architecture names and compile options used are only provided for Intel Core series.
Even the newest Pentium and Celeron CPUs are often missing features.

#### NOTE:
The archive contains all respective binaries for many different CPU types!
Use the native version if you are not sure of the type of CPU instruction set for your CPU.

#### WINDOWS ARCH EXE NOTE:
Use your respective architecture .exe per your processor's instruction set!

64Bit Exe name	|		Compile flags		|	Arch name
------------ | -------------| -------------
urx-isotope-cpuminer.exe | "-march=native" | Native
urx-isotope-cpuminer-avx512.exe | "-march=skylake-avx512" | Skylake
urx-isotope-cpuminer-avx2.exe | "-march=core-avx2" | Haswell, Sky-Kaby-Coffeelake
urx-isotope-cpuminer-avx.exe | "-march=corei7-avx" | Sandy-Ivybridge
urx-isotope-cpuminer-sse42.exe | "-march=westmere" | Westmere
urx-isotope-cpuminer-sse2.exe | "-msse2" | Core2, Nehalem
urx-isotope-cpuminer-ryzen.exe | "-march=znver1" | Ryzen

##### DROPPED SUPPORT in version v1.0.4
64Bit Exe name	|		Compile flags		|	Arch name
------------ | -------------| -------------
//urx-isotope-cpuminer-dryzen.exe | "-march=znver1 -DRYZEN_" | Ryzen


#### UBUNTU 18.04 LINUX ARCH NOTE:
Use your respective architecture per your processor's instruction set!

64Bit Exe name	|		Compile flags		|	Arch name
------------ | -------------| -------------
urx-isotope-cpuminer | "-march=native" | Native
urx-isotope-cpuminer-avx512 | "-march=skylake-avx512" | Skylake
urx-isotope-cpuminer-avx | "-march=corei7-avx" | Sandy-Ivybridge
urx-isotope-cpuminer-avx2 | "-march=core-avx2" | Haswell, Sky-Kaby-Coffeelake
urx-isotope-cpuminer-sse42 | "-march=westmere" | Westmere
urx-isotope-cpuminer-sse2 | "-msse2" | Core2, Nehalem
urx-isotope-cpuminer-ryzen.exe | "-march=znver1" | Ryzen

##### DROPPED SUPPORT in version v1.0.4
64Bit Exe name	|		Compile flags		|	Arch name
------------ | -------------| -------------
//urx-isotope-cpuminer-dryzen | "-march=znver1 -DRYZEN_" | Ryzen

#### NOTE:
The following tips may be useful for older AMD CPUs.

AMD CPUs older than Steamroller, including Athlon x2 and Phenom II x4, are
not supported by urx-isotope-cpuminer due to an incompatible implementation of SSE2
on these CPUs.
Some algos may crash the miner with an invalid instruction.
Users are recommended to use an unoptimized miner such as cpuminer-multi.

Some users with AMD CPUs without AES_NI have reported problems compiling
with build.sh or "-march=native".
Problems have included compile errors and poor performance.
These users are recommended to compile manually specifying "-march=btver1" on the configure
command line.

### Support for even older x86_64 without AES_NI or SSE2 is not availble.

#### Isotope Crypto  ( ͡° ͜ʖ ͡°)

#### Supported Algorithms

                          allium        Garlicoin
                          anime         Animecoin
                          argon2        Argon2 coin (AR2)
                          argon2d250    argon2d-crds, Credits (CRDS)
                          argon2d500    argon2d-dyn,  Dynamic (DYN)
                          argon2d4096   argon2d-uis, Unitus, (UIS)
                          axiom         Shabal-256 MemoHash
                          bastion
                          blake         Blake-256 (SFR)
                          blakecoin     blake256r8
                          blake2s       Blake-2 S
                          bmw           BMW 256
                          c11           Chaincoin
                          cryptolight   Cryptonight-light
                          cryptonight  
                          cryptonightv7 Monero (XMR)
                          decred
                          deep          Deepcoin (DCN)
                          dmd-gr        Diamond-Groestl
                          drop          Dropcoin
                          fresh         Fresh
                          groestl       Groestl coin
                          heavy         Heavy
                          hmq1725       Espers
                          hodl          Hodlcoin
                          jha           Jackpotcoin
                          keccak        Maxcoin
                          keccakc       Creative coin
                          lbry          LBC, LBRY Credits
                          luffa         Luffa
                          lyra2h        Hppcoin
                          lyra2re       lyra2
                          lyra2rev2     lyra2v2, Vertcoin
                          lyra2rev3     lyrav2v3, Vertcoin
                          lyra2z        Zcoin (XZC)
                          lyra2z330     Lyra2 330 rows, Zoin (ZOI)
                          m7m           Magi (XMG)
                          myr-gr        Myriad-Groestl
                          neoscrypt     NeoScrypt(128, 2, 1)
                          nist5         Nist5
                          pentablake    Pentablake
                          phi1612       phi, LUX coin (original algo)
                          phi2          LUX coin (new algo)
                          pluck         Pluck:128 (Supcoin)
                          polytimos     Ninja
                          quark         Quark
                          qubit         Qubit
                          scrypt        scrypt(1024, 1, 1) (default)
                          scrypt:N      scrypt(N, 1, 1)
                          scryptjane:nf
                          sha256d       Double SHA-256
                          sha256t       Triple SHA-256, Onecoin (OC)
                          shavite3      Shavite3
                          skein         Skein+Sha (Skeincoin)
                          skein2        Double Skein (Woodcoin)
                          skunk         Signatum (SIGT)
                          sonoa         Sono
                          timetravel    Machinecoin (MAC)
                          timetravel10  Bitcore
                          tribus        Denarius (DNR)
                          vanilla       blake256r8vnl (VCash)
                          veltor        (VLT)
                          whirlpool
                          whirlpoolx
                          x11           Dash
                          x11evo        Revolvercoin
                          x11gost       sib (SibCoin)
                          x12           Galaxie Cash (GCH)
                          x13           X13
                          x13sm3        hsr (Hshare)
                          x14           X14
                          x15           X15
                          x16r          Ravencoin (RVN)
                          x16s          pigeoncoin (PGN)
                          x17
                          xevan         Bitsend (BSD)
                          yescrypt      Globalboost-Y (BSTY)
                          yescryptr8    BitZeny (ZNY)
                          yescryptr16   Eli
                          yescryptr32   WAVI
                          yespower      Cryply
                          yespowerr16   Yenten (YTN)
                          yespowerurx   UraniumX (URX)
                          zr5           Ziftr
