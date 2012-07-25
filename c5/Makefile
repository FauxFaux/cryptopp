CC = cl /nologo /EHsc /MT /O2 /W2 /Oi /GL

SRCS = 3way.cpp adler32.cpp algebra.cpp algparam.cpp arc4.cpp asn.cpp authenc.cpp base32.cpp base64.cpp basecode.cpp bench.cpp bench2.cpp bfinit.cpp blowfish.cpp blumshub.cpp camellia.cpp cast.cpp casts.cpp cbcmac.cpp ccm.cpp channels.cpp cmac.cpp cpu.cpp crc.cpp cryptlib.cpp cryptlib_bds.cpp datatest.cpp default.cpp des.cpp dessp.cpp dh.cpp dh2.cpp dll.cpp dlltest.cpp dsa.cpp eax.cpp ec2n.cpp eccrypto.cpp ecp.cpp elgamal.cpp emsa2.cpp eprecomp.cpp esign.cpp files.cpp filters.cpp fips140.cpp fipsalgt.cpp fipstest.cpp gcm.cpp gf256.cpp gf2_32.cpp gf2n.cpp gfpcrypt.cpp gost.cpp gzip.cpp hex.cpp hmac.cpp hrtimer.cpp ida.cpp idea.cpp integer.cpp iterhash.cpp luc.cpp mars.cpp marss.cpp md2.cpp md4.cpp md5.cpp misc.cpp modes.cpp mqueue.cpp mqv.cpp nbtheory.cpp network.cpp oaep.cpp osrng.cpp panama.cpp pch.cpp pkcspad.cpp polynomi.cpp pssr.cpp pubkey.cpp queue.cpp rabin.cpp randpool.cpp rc2.cpp rc5.cpp rc6.cpp rdtables.cpp regtest.cpp rijndael.cpp ripemd.cpp rng.cpp rsa.cpp rw.cpp safer.cpp salsa.cpp seal.cpp seed.cpp serpent.cpp sha.cpp shacal2.cpp shark.cpp sharkbox.cpp simple.cpp skipjack.cpp socketft.cpp sosemanuk.cpp square.cpp squaretb.cpp strciphr.cpp tea.cpp test.cpp tftables.cpp tiger.cpp tigertab.cpp trdlocal.cpp ttmac.cpp twofish.cpp validat1.cpp validat2.cpp validat3.cpp vmac.cpp wait.cpp wake.cpp whrlpool.cpp winpipes.cpp xtr.cpp xtrcrypt.cpp zdeflate.cpp zinflate.cpp zlib.cpp
OBJS = 3way.obj adler32.obj algebra.obj algparam.obj arc4.obj asn.obj authenc.obj base32.obj base64.obj basecode.obj bench.obj bench2.obj bfinit.obj blowfish.obj blumshub.obj camellia.obj cast.obj casts.obj cbcmac.obj ccm.obj channels.obj cmac.obj cpu.obj crc.obj cryptlib.obj cryptlib_bds.obj datatest.obj default.obj des.obj dessp.obj dh.obj dh2.obj dll.obj dlltest.obj dsa.obj eax.obj ec2n.obj eccrypto.obj ecp.obj elgamal.obj emsa2.obj eprecomp.obj esign.obj files.obj filters.obj fips140.obj fipsalgt.obj fipstest.obj gcm.obj gf256.obj gf2_32.obj gf2n.obj gfpcrypt.obj gost.obj gzip.obj hex.obj hmac.obj hrtimer.obj ida.obj idea.obj integer.obj iterhash.obj luc.obj mars.obj marss.obj md2.obj md4.obj md5.obj misc.obj modes.obj mqueue.obj mqv.obj nbtheory.obj network.obj oaep.obj osrng.obj panama.obj pch.obj pkcspad.obj polynomi.obj pssr.obj pubkey.obj queue.obj rabin.obj randpool.obj rc2.obj rc5.obj rc6.obj rdtables.obj regtest.obj rijndael.obj ripemd.obj rng.obj rsa.obj rw.obj safer.obj salsa.obj seal.obj seed.obj serpent.obj sha.obj shacal2.obj shark.obj sharkbox.obj simple.obj skipjack.obj socketft.obj sosemanuk.obj square.obj squaretb.obj strciphr.obj tea.obj test.obj tftables.obj tiger.obj tigertab.obj trdlocal.obj ttmac.obj twofish.obj validat1.obj validat2.obj validat3.obj vmac.obj wait.obj wake.obj whrlpool.obj winpipes.obj xtr.obj xtrcrypt.obj zdeflate.obj zinflate.obj zlib.obj x64dll.obj x64masm.obj

all: cryptest.exe

test: cryptest.exe
	./cryptest.exe v

.cpp.obj:
	$(CC) /c $*.cpp
	$(MT)

.asm.obj:
	ml64 /nologo /c $*.asm /Fo$*.obj
	
libcryptopp.lib: $(OBJS)
	lib /out:$@ /ltcg $(OBJS)

cryptest.exe: libcryptopp.lib
	$(CC) /Fe$@ ./libcryptopp.lib test.obj ws2_32.lib

clean:
	del *.obj
	del *.lib
	del *.exe
	del *.pdb