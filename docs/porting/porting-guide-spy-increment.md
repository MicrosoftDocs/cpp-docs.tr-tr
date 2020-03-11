---
title: 'Taşıma Kılavuzu: Spy++'
ms.date: 10/23/2019
ms.assetid: e558f759-3017-48a7-95a9-b5b779d5e51d
ms.openlocfilehash: 5505e0dbf23dd02f4ae5924ff4f2bacff3f11eea
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78890947"
---
# <a name="porting-guide-spy"></a>Taşıma Kılavuzu: Spy++

Bu taşıma olay incelemesi, tipik bir taşıma projesinin ne olduğu, karşılaşabileceğiniz sorun türleri ve taşıma sorunlarını gidermeye yönelik bazı genel ipuçları ve püf noktaları hakkında fikir vermek için tasarlanmıştır. Bir projenin taşıma deneyimi kodun ayrıntılarına çok daha fazla bağlı olduğundan, taşıma işlemi için kesin bir kılavuz olması amaçlıyordu.

## <a name="spy"></a>Spy++

Spy + +, Windows Masaüstü için Kullanıcı arabirimi öğeleriyle ilgili her türlü bilgiyi sağlayan, yaygın olarak kullanılan bir GUI tanılama aracıdır. Windows 'un tüm hiyerarşisini gösterir ve her pencere ve denetimle ilgili meta verilere erişim sağlar. Bu faydalı uygulama birçok yıl boyunca Visual Studio ile birlikte gönderilmiştir. Visual C++ 6,0 ' de en son derlenen ve visual Studio 2015 ' e geçen eski bir sürümü bulduk. Visual Studio 2017 veya Visual Studio 2019 deneyimi neredeyse aynı olmalıdır.

Bu durum, özellikle Visual C++ C++ 6,0 ' den bu yana Visual 'in her sürümüyle GÜNCELLEŞTIRILMEMIŞ eski projeler için MFC ve Win32 API kullanan Windows masaüstü uygulamalarını taşıma için tipik olarak kabul ettik.

##  <a name="convert_project_file"></a>1. adım. Proje dosyası dönüştürülüyor.

Visual C++ 6,0 ' deki iki eski. DSW dosyası olan proje dosyası, daha fazla dikkat gerektiren sorunlar olmadan kolayca dönüştürülür. Bir proje Spy + + uygulamasıdır. Diğeri, destekleyen bir DLL olan C dilinde yazılmış SpyHk. [Burada](../porting/visual-cpp-porting-and-upgrading-guide.md)açıklandığı gibi daha karmaşık projeler kolayca yükseltilmeyebilir.

İki proje yükseltildikten sonra çözümümüzü şöyle inceledik:

![Spy&#43; &#43; çözümü](../porting/media/spyxxsolution.PNG "Spy&#43; &#43; çözümü")

Biri çok sayıda C++ dosya Içeren ve C dilinde yazılmış başka bir dll olmak üzere iki projeniz vardır.

##  <a name="header_file_problems"></a>2. adım. Üstbilgi dosyası sorunları

Yeni dönüştürülen bir proje oluştururken, genellikle bulacağınız ilk şey, projenizin kullandığı başlık dosyalarının bulunamadığını halledir.

Spy + + ' da bulunamayan dosyalardan biri verstamp. h idi. Bir Internet aramadan, bunun eski bir veri teknolojisi olan bir DAO SDK 'dan geldiğini belirledik. Bu dosyanın gerçekten gerekli olup olmadığını görmek için, bu üst bilgi dosyasından hangi simgelerin kullanıldığını öğrenmek istiyorduk. bu nedenle, üst bilgi dosyası bildirimini yorumlarız ve yeniden derlenir. Yalnızca gerekli olan tek bir sembol vardır VER_FILEFLAGSMASK.

```Output
1>C:\Program Files (x86)\Windows Kits\8.1\Include\shared\common.ver(212): error RC2104: undefined keyword or key name: VER_FILEFLAGSMASK
```

Kullanılabilir içerme dosyalarında bir sembol bulmanın en kolay yolu, **dosyalarda bul** (**Ctrl**+**SHIFT**+**F**) öğesini kullanmak ve **görsel C++ ekleme dizinlerini**belirtmektir. Bunu ntverp. h içinde bulduk. Verdamgamız. h dahil olmak üzere ntverp. h ile değiştirilmiştir ve bu hata kayboldu.

##  <a name="linker_output_settings"></a>3. adım. Bağlayıcı ÇıktıDosyası ayarı

Daha eski projeler bazen, yükseltmeden sonra sorunlara neden olabilecek geleneksel konumlara yerleştirilmiş dosyalardır. Bu durumda, Visual Studio 'Nun proje klasörlerinden birine değil, orada yer alan bazı üst bilgi dosyalarını bulabileceğinden emin olmak için proje özelliklerinde **ekleme** yoluna `$(SolutionDir)` eklememiz gerekir.

MSBuild şikayetleri **Link. ÇıktıDosyası** ÖZELLIĞININ, MSB8012 veren **targetPath** ve **TargetName** değerleriyle eşleşmez.

```Output
warning MSB8012: TargetPath(...\spyxx\spyxxhk\.\..\Debug\SpyxxHk.dll) does not match the Linker's OutputFile property value (...\spyxx\Debug\SpyHk55.dll). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).warning MSB8012: TargetName(SpyxxHk) does not match the Linker's OutputFile property value (SpyHk55). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).
```

**LINK. çıkışdosyası** , derleme çıktıdır (ÖRNEĞIN, exe, dll) ve normalde `$(TargetDir)$(TargetName)$(TargetExt)`tarafından oluşturulur ve bu yol, dosya adı ve uzantı sağlar. Bu, eski görsel C++ derleme aracından (VCBuild. exe) projeleri yeni derleme aracına (MSBuild. exe) geçirirken yaygın bir hatadır. Visual Studio 2010 ' de derleme aracı değişikliği gerçekleştiği için, önce 2010 bir projeyi 2010 veya sonraki bir sürüme geçirdiğinizde bu sorunla karşılaşabilirsiniz. Temel sorun, projenin diğer proje ayarlarına dayanmasından ne olduğunu belirlemek için her zaman mümkün olmadığından, proje Geçiş Sihirbazı 'nın **LINK. çıkışdosyası** değerini güncelleştirmemesinden bağımsız olur. Bu nedenle, genellikle el ile ayarlamanız gerekir. Daha fazla ayrıntı için, Visual C++ blogda bu [gönderisine](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/) bakın.

Bu durumda, yapılandırmaya bağlı olarak, dönüştürülen projedeki **Link. ÇıktıDosyası** özelliği Spy + + projesi için .\Debug\Spyxx.exe ve .\Release\Spyxx.exe olarak ayarlanmıştır. En iyi sonuç, bu sabit kodlanmış değerleri **Tüm yapılandırmalarda**`$(TargetDir)$(TargetName)$(TargetExt)` değiştirmek olacaktır. Bu işe yaramazsa, bu değerlerin ayarlandığı **genel** bölümdeki Özellikler ' i buradan özelleştirebilir veya ( **çıkış dizini**, **hedef adı**ve **hedef uzantısı**) özellikleri değiştirebilirsiniz. Görüntülemekte olduğunuz özellik makrolar kullanıyorsa, açılan listede **Düzenle** ' yi seçerek, makro değişimlerin yaptığı son dizeyi gösteren bir iletişim kutusu açabilirsiniz. **Makrolar** düğmesini seçerek kullanılabilir tüm makroları ve bunların geçerli değerlerini görüntüleyebilirsiniz.

##  <a name="updating_winver"></a>4. adım. Hedef Windows sürümü güncelleştiriliyor

Sonraki hata, WINVER sürümünün MFC 'de artık desteklenmediğini gösterir. Windows XP için WINVER 0x0501.

```Output
C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxv_w32.h(40): fatal error C1189: #error:  MFC does not support WINVER less than 0x0501.  Please change the definition of WINVER in your project properties or precompiled header.
```

Windows XP artık Microsoft tarafından desteklenmemektedir. bu nedenle, Visual Studio 'da izin verilmesini hedefleyerek, uygulamalarınızda BT için destek sahibi olmanız ve kullanıcılarınıza Windows 'un yeni sürümlerini benimsemeleri teşvik.

Hatadan kurtulmak için, **Proje özellikleri** ayarını Şu anda hedeflemek istediğiniz en düşük Windows sürümüne güncelleştirerek WINVER tanımlayın. [Burada](/windows/win32/WinProg/using-the-windows-headers)çeşitli Windows sürümleri için bir değer tablosu bulun.

*Stbafx. h* dosyası bu makro tanımlarından bazılarını içeriyordu.

```cpp
#define WINVER       0x0500  // these defines are set so that we get the
#define _WIN32_WINNT 0x0500  // maximum set of message/flag definitions,
#define _WIN32_IE    0x0400  // from both winuser.h and commctrl.h.
```

WINVER, Windows 7 olarak ayarlayacağız. Değerin kendisi yerine Windows 7 (_WIN32_WINNT_WIN7) makrosunu kullanıyorsanız kodu daha sonra okumak daha kolaydır (0x0601).

```cpp
#define WINVER _WINNT_WIN32_WIN7 // Minimum targeted Windows version is Windows 7
```

##  <a name="linker_errors"></a>5. adım. Bağlayıcı hataları

Bu değişikliklerle, SpyHk (DLL) projesi oluşturulur ancak bir bağlayıcı hatası üretir.

```Output
LINK : warning LNK4216: Exported entry point _DLLEntryPoint@12
```

DLL için giriş noktası aktarılmamalıdır. Giriş noktası yalnızca, DLL ilk olarak belleğe yüklendiğinde yükleyici tarafından çağrılmalıdır. bu nedenle, diğer çağıranlar için olan dışarı aktarma tablosunda olmaması gerekir. Kendisine iliştirilmiş **__declspec (dllexport)** yönergesini içermediğinden emin olmak istiyoruz. Spyxxhk. c ' de, bunu iki yerden, `DLLEntryPoint`bildirimi ve tanımını kaldırdık. Bu yönergeyi kullanmanın hiçbir anlamı yoktur, ancak bağlayıcı ve derleyicinin önceki sürümleri sorun olarak bayrak almadı. Bağlayıcının daha yeni sürümleri bir uyarı verir.

```cpp
// deleted __declspec(dllexport)
BOOL WINAPI DLLEntryPoint(HINSTANCE hinstDLL,DWORD fdwReason, LPVOID lpvReserved);
```

C DLL projesi, SpyHK. dll, artık hata olmadan derleme ve bağlantı.

##  <a name="outdated_header_files"></a>Adım 6. Daha güncel olmayan başlık dosyaları

Bu noktada, spyxx ana yürütülebilir projesi üzerinde çalışmaya başladık.

Diğer birkaç içerme dosyası bulunamadı: ctl3d. h ve penwin. h. Üstbilginin ne olduğunu belirlemeyi denemek için Internet 'te arama yapmak faydalı olabilir, bazen bilgiler yararlı değildir. Bu ctl3d. h 'nin Exchange geliştirme seti 'nin bir parçası olduğunu ve Windows 95 ' de belirli bir denetim stili olduğunu ve penwin. h ' nin, eski bir API ile pencere kalemi Bilgi Işlem ile ilişkili olduğunu bulduk. Bu durumda, `#include` satırını açıklamamız ve verkadamgası. h ile yaptığımız tanımsız simgelerle uğraştık. 3B denetimlerle veya kalem Bilgi Işlem ile ilgili her şey projeden kaldırılmıştır.

Aşamalı olarak ortadan kaldırdığınız çok sayıda derleme hatası olan bir proje verildiğinde, `#include` yönergesini kaldırdığınızda güncel olmayan bir API 'nin tüm kullanımlarını bulmak gerçekçi değildir. Bu işlemi hemen algılamadık, ancak daha sonraki bir noktada WM_DLGBORDER tanımsız bir hataya geldi. Bu, ctl3d. h ' den gelen tanımsız simgelerden yalnızca biridir. Süresi geçmiş bir API ile ilgili olduğunu belirledikten sonra, koddaki tüm başvuruları kaldırdık.

##  <a name="updating_iostreams_code"></a>7. adım. Eski Iostreams kodu güncelleştiriliyor

Sonraki hata, Iostreams kullanan eski C++ kodla yaygındır.

```Output
mstream.h(40): fatal error C1083: Cannot open include file: 'iostream.h': No such file or directory
```

Bu sorun, eski Iostreams kitaplığının kaldırılıp değiştirildiği yerdir. Eski Iostreams 'ı daha yeni standartlara göre değiştirmek istiyoruz.

```cpp
#include <iostream.h>
#include <strstrea.h>
#include <iomanip.h>
```

Bunlar şu şekilde bulunur:

```cpp
#include <iostream>
#include <sstream>
#include <iomanip>
```

Bu değişiklik ile artık kullanılmayan `ostrstream`sorunlarla karşılaştık. Uygun değişiklik ostringstream 'dir. Kodu çok büyük, en azından bir başlangıç olarak değiştirmeyi önlemek için `ostrstream` için bir **typedef** eklemeyi denedik.

```cpp
typedef std::basic_ostringstream<TCHAR> ostrstream;
```

Şu anda proje MBCS (çok baytlık karakter kümesi) kullanılarak oluşturulmuştur, bu nedenle **char** uygun karakter veri türüdür. Ancak, kodu UTF-16 Unicode 'a daha kolay bir şekilde güncelleştirmeye izin vermek için bunu, proje ayarlarındaki **karakter kümesi** özelliğinin MBCS veya Unicode olarak ayarlanmış olmasına bağlı olarak **char** veya **wchar_t** olarak çözümlenen `TCHAR`güncelleştiririz.

Birkaç başka kod parçasının güncellenmesi gerekiyor.  Temel sınıf `ios` `ios_base`ile değiştirdik ve ostream ' i basic_ostream\<T > olarak değiştirdik. İki ek Typedefs ekleyeceğiz ve bu bölüm derlenir.

```cpp
typedef std::basic_ostream<TCHAR> ostream;
typedef ios_base ios;
```

Bu tür tanımları 'ın kullanılması yalnızca geçici bir çözümdür. Daha kalıcı bir çözüm için, her başvuruyu yeniden adlandırılmış veya eski API 'ye güncelleştirebiliriz.

İşte bir sonraki hata.

```Output
error C2039: 'freeze': is not a member of 'std::basic_stringbuf<char,std::char_traits<char>,std::allocator<char>>'
```

Bir sonraki sorun `basic_stringbuf` `freeze` yöntemine sahip değildir. `freeze` yöntemi, eski `ostream`bellek sızıntısına engel olmak için kullanılır. Artık yeni `ostringstream`kullandığımıza gerek kalmaz. `freeze`çağrısı silinebilir.

```cpp
//rdbuf()->freeze(0);
```

Bitişik satırlarda sonraki iki hata oluştu. Bir dizeye null Sonlandırıcı ekleyen eski `iostream` kitaplığının GÇ işleyicisi olan `ends`kullanmaya yönelik ilk şikayet. Bu hataların saniyesi `str` yönteminin çıkışının const olmayan bir işaretçiye atanmadığı açıklanmaktadır.

```cpp
// Null terminate the string in the buffer and
// get a pointer to it.
//
*this << ends;
LPSTR psz = str();
```

```Output
2>mstream.cpp(167): error C2065: 'ends': undeclared identifier2>mstream.cpp(168): error C2440: 'initializing': cannot convert from 'std::basic_string<char,std::char_traits<char>,std::allocator<char>>' to 'LPSTR'
```

Yeni akış kitaplığını kullanarak, dizenin her zaman null sonlandırıldığı için `ends`, bu satır kaldırılabileceği için gerekli değildir. İkinci sorun için, sorun artık `str()` bir dizenin karakter dizisine bir işaretçi döndürmemelidir; `std::string` türünü döndürür. İkinci çözüm, türü `LPCSTR` olarak değiştirmek ve işaretçiyi istemek için `c_str()` metodunu kullanmaktır.

```cpp
//*this << ends;
LPCTSTR psz = str().c_str();
```

Bu kodda puzzled bizimle ilgili bir hata oluştu.

```cpp
MOUT << _T(" chUser:'") << chUser
<< _T("' (") << (INT)(UCHAR)chUser << _T(')');
```

MOUT makrosu, `mstream`türünde bir nesne olan `*g_pmout` çözümleniyor. `mstream` sınıfı, `std::basic_ostream<TCHAR>`standart çıkış dizesi sınıfından türetilir. Ancak, Unicode 'a dönüştürmeye hazırlanmaya koyduğumuz dize sabit değeri etrafında \_T ile **< < işleç** için aşırı yükleme çözümlemesi aşağıdaki hata iletisiyle başarısız olur:

```Output
1>winmsgs.cpp(4612): error C2666: 'mstream::operator <<': 2 overloads have similar conversions
1>  c:\source\spyxx\spyxx\mstream.h(120): note: could be 'mstream &mstream::operator <<(ios &(__cdecl *)(ios &))'
1>  c:\source\spyxx\spyxx\mstream.h(118): note: or       'mstream &mstream::operator <<(ostream &(__cdecl *)(ostream &))'
1>  c:\source\spyxx\spyxx\mstream.h(116): note: or       'mstream &mstream::operator <<(ostrstream &(__cdecl *)(ostrstream &))'
1>  c:\source\spyxx\spyxx\mstream.h(114): note: or       'mstream &mstream::operator <<(mstream &(__cdecl *)(mstream &))'
1>  c:\source\spyxx\spyxx\mstream.h(109): note: or       'mstream &mstream::operator <<(LPTSTR)'
1>  c:\source\spyxx\spyxx\mstream.h(104): note: or       'mstream &mstream::operator <<(TCHAR)'
1>  c:\source\spyxx\spyxx\mstream.h(102): note: or       'mstream &mstream::operator <<(DWORD)'
1>  c:\source\spyxx\spyxx\mstream.h(101): note: or       'mstream &mstream::operator <<(WORD)'
1>  c:\source\spyxx\spyxx\mstream.h(100): note: or       'mstream &mstream::operator <<(BYTE)'
1>  c:\source\spyxx\spyxx\mstream.h(95): note: or       'mstream &mstream::operator <<(long)'
1>  c:\source\spyxx\spyxx\mstream.h(90): note: or       'mstream &mstream::operator <<(unsigned int)'
1>  c:\source\spyxx\spyxx\mstream.h(85): note: or       'mstream &mstream::operator <<(int)'
1>  c:\source\spyxx\spyxx\mstream.h(83): note: or       'mstream &mstream::operator <<(HWND)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1132): note: or       'CDumpContext &operator <<(CDumpContext &,COleSafeArray &)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1044): note: or       'CArchive &operator <<(CArchive &,ATL::COleDateTimeSpan)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1042): note: or       'CDumpContext &operator <<(CDumpContext &,ATL::COleDateTimeSpan)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1037): note: or       'CArchive &operator <<(CArchive &,ATL::COleDateTime)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1035): note: or       'CDumpContext &operator <<(CDumpContext &,ATL::COleDateTime)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1030): note: or       'CArchive &operator <<(CArchive &,COleCurrency)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(1028): note: or       'CDumpContext &operator <<(CDumpContext &,COleCurrency)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(955): note: or       'CArchive &operator <<(CArchive &,ATL::CComBSTR)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(951): note: or       'CArchive &operator <<(CArchive &,COleVariant)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxdisp.h(949): note: or       'CDumpContext &operator <<(CDumpContext &,COleVariant)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(248): note: or       'CArchive &operator <<(CArchive &,const RECT &)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(247): note: or       'CArchive &operator <<(CArchive &,POINT)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(246): note: or       'CArchive &operator <<(CArchive &,SIZE)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(242): note: or       'CDumpContext &operator <<(CDumpContext &,const RECT &)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(241): note: or       'CDumpContext &operator <<(CDumpContext &,POINT)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxwin.h(240): note: or       'CDumpContext &operator <<(CDumpContext &,SIZE)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1639): note: or       'CArchive &operator <<(CArchive &,const CObject *)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1425): note: or       'CArchive &operator <<(CArchive &,ATL::CTime)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1423): note: or       'CDumpContext &operator <<(CDumpContext &,ATL::CTime)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1418): note: or       'CArchive &operator <<(CArchive &,ATL::CTimeSpan)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afx.h(1416): note: or       'CDumpContext &operator <<(CDumpContext &,ATL::CTimeSpan)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(694): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,const char *)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(741): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,char)'
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(866): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,const _Elem *)'
1>          with
1>          [
1>              _Elem=wchar_t
1>          ]
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(983): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>,wchar_t[10]>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &&,const _Ty (&))'
1>          with
1>          [
1>              _Ty=wchar_t [10]
1>          ]
1>  C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\include\ostream(1021): note: or       'std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &std::operator <<<wchar_t,std::char_traits<wchar_t>>(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,const std::error_code &)'
1>  winmsgs.cpp(4612): note: while trying to match the argument list '(CMsgStream, const wchar_t [10])'
```

Bu tür bir hata **<** tanımı, bu tür bir hatanın önleyilebilmesini < çok sayıda operatör vardır. Kullanılabilir aşırı yüklerden daha yakından bakdıktan sonra, bunların çoğunun ilgisiz olduğunu ve `mstream` sınıf tanımına daha yakından bakmadığımızda, bu durumda çağrılması gerektiğini düşündüğdiğimiz aşağıdaki işlevi belirledik.

```cpp
mstream& operator<<(LPTSTR psz)
{
  return (mstream&)ostrstream::operator<<(psz);
}
```

Çağrılmadığı neden, bu uzun hata iletisinin son satırından görebileceğiniz gibi `const wchar_t[10]` dize değişmez değeri, bu nedenle const olmayan bir işaretçiye dönüştürme otomatik değildir. Ancak, bu operatör giriş parametresini değiştirmemelidir. bu nedenle, daha uygun parametre türü `LPCTSTR` (MBCS olarak derlerken`const char*` ve Unicode olarak `const wchar_t*`), `LPTSTR` değil (MBCS olarak derlerken`char*` ve `wchar_t*` Unicode olarak derlenirken). Bu değişikliğin yapılması bu hatayı düzeltir.

Bu tür dönüştürmeye daha eski, daha az sıkı derleyici altında izin verilir, ancak daha son uygunluk değişiklikleri daha doğru kod gerektirir.

##  <a name="stricter_conversions"></a>8. adım. Derleyicinin daha katı dönüşümler

Aşağıdakiler gibi birçok hata da sunuyoruz:

```Output
error C2440: 'static_cast': cannot convert from 'UINT (__thiscall CHotLinkCtrl::* )(CPoint)' to 'LRESULT (__thiscall CWnd::* )(CPoint)'
```

Hata yalnızca makro olan bir ileti eşlemesinde oluşur:

```cpp
BEGIN_MESSAGE_MAP(CFindToolIcon, CWnd)
// other messages omitted...
ON_WM_NCHITTEST() // Error occurs on this line.
END_MESSAGE_MAP()
```

Bu makronun tanımına giderek `OnNcHitTest`işlevine başvurduğumuz görüyoruz.

```cpp
#define ON_WM_NCHITTEST() \
{ WM_NCHITTEST, 0, 0, 0, AfxSig_l_p, \
(AFX_PMSG)(AFX_PMSGW) \
(static_cast< LRESULT (AFX_MSG_CALL CWnd::*)(CPoint) > (&ThisClass :: OnNcHitTest)) },
```

Bu sorun, üye işlev türlerine yönelik işaretçiyle uyuşmuyor. Sorun, geçerli bir türetilmiş-temel dönüştürme olduğundan, sınıf türü olarak `CWnd` `CHotLinkCtrl` bir sınıf türü olarak bir dönüştürme değildir. Sorun, dönüş türü: UINT vs. LRESULT. LRESULT, hedef ikili türüne bağlı olarak 64 bitlik bir işaretçi ya da 32-bit işaretçisi olan LONG_PTR çözümlendiğinden, UINT bu türe dönüştürmez. Bu, bir çok ileti eşleme yönteminin dönüş türü, Visual Studio 2005 ' de 64-bit uyumluluk değişikliklerinin bir parçası olarak değiştiğinden, bu nedenle 2005 ' dan önce yazılan kodu yükseltirken sık görülen bir durumdur. Aşağıdaki koddaki UINT olan dönüş türünü LRESULT olarak değiştirdik:

```cpp
afx_msg UINT OnNcHitTest(CPoint point);
```

Değişiklikten sonra aşağıdaki kodu sunuyoruz:

```cpp
afx_msg LRESULT OnNcHitTest(CPoint point);
```

Bu işlevin, CWnd 'den türetilmiş farklı sınıflarda her biri yaklaşık on tekrardan oluştuğundan, imleç düzenleyiciyle ilgili olarak simgeye git (klavye: **F12**) ve **bildirim** ' ı (klavye: **CTRL**+**F12**) kullanın ve **sembol bul** araç penceresinde bunlara gidebilirsiniz. **Tanıma Git** genellikle ikiden fazla yararlı olur. **Bildirimine git** , friend sınıfı bildirimleri veya iletme başvuruları gibi tanımlayıcı sınıf bildirimi dışındaki bildirimleri bulur.

##  <a name="mfc_changes"></a>9. adım. MFC değişiklikleri

Sonraki hata ayrıca değiştirilmiş bir bildirim türüyle ilgilidir ve aynı zamanda bir makroda de gerçekleşir.

```Output
error C2440: 'static_cast': cannot convert from 'void (__thiscall CFindWindowDlg::* )(BOOL,HTASK)' to 'void (__thiscall CWnd::* )(BOOL,DWORD)'
```

Sorun, `CWnd::OnActivateApp` ikinci parametresi HTASK 'dan DWORD 'e değiştirilvidir. Bu değişiklik, Visual Studio 'nun 2002 sürümünde (Visual Studio .NET) oluştu.

```cpp
afx_msg void OnActivateApp(BOOL bActive, HTASK hTask);
```

Türetilmiş sınıflarda OnActivateApp bildirimlerini aşağıdaki gibi güncelleştirmemiz gerekir:

```cpp
afx_msg void OnActivateApp(BOOL bActive, DWORD dwThreadId);
```

Bu noktada, projeyi derleyebiliriz. Bununla birlikte çalışmak için birkaç uyarı vardır; ancak, MBCS 'den Unicode 'a dönüştürme veya güvenli CRT işlevlerini kullanarak güvenliği artırma gibi, yükseltmenin isteğe bağlı bölümleri vardır.

##  <a name="compiler_warnings"></a>10. adım. Derleyici uyarılarını adresleme

Uyarıların tam listesini almak için, yalnızca geçerli derlemeden uyarı raporları aldığınızdan, yalnızca derlenmiş olan her şeyin yeniden derlendiğinden emin olmak için, normal derleme yerine çözüm üzerinde **tümünü yeniden derle** yapmanız gerekir. Diğer soru, geçerli Uyarı düzeyinin kabul edilip edilmeyeceğini veya daha yüksek bir uyarı düzeyi kullanılmasını sağlar.  Büyük bir kod taşıma sırasında, özellikle eski kod, daha yüksek bir uyarı düzeyi kullanılarak uygun olabilir.  Ayrıca, varsayılan uyarı düzeyiyle başlamak ve tüm uyarıları almak için uyarı düzeyini artırmak isteyebilirsiniz. `/Wall`kullanıyorsanız, sistem üstbilgi dosyalarında bazı uyarılar alırsınız, böylece birçok kişi, sistem üstbilgileri için uyarı almadan kendi kodlarında en iyi uyarıları almak üzere `/W4` kullanır. Uyarıların hata olarak gösterilmesini istiyorsanız `/WX` seçeneğini ekleyin. Bu ayarlar, **Proje özellikleri** iletişim kutusunun **C/C++**  bölümünde bulunur.

`CSpyApp` sınıfındaki yöntemlerden biri, artık desteklenmeyen bir işlev hakkında uyarı oluşturur.

```cpp
void SetDialogBkColor() {CWinApp::SetDialogBkColor(::GetSysColor(COLOR_BTNFACE));}
```

Uyarı aşağıdaki gibidir.

```Output
warning C4996: 'CWinApp::SetDialogBkColor': CWinApp::SetDialogBkColor is no longer supported. Instead, handle WM_CTLCOLORDLG in your dialog
```

WM_CTLCOLORDLG ileti, Spy + + kodunda zaten işlendi. bu nedenle, gerekli tek değişiklik, artık gerekli olmayan `SetDialogBkColor`başvurularını silmektir.

Sonraki uyarı, değişken adını açıklama ekleyerek düzeltilmesi basittir. Şu uyarıyı aldık:

```Output
warning C4456: declaration of 'lpszBuffer' hides previous local declaration
```

Bunu üreten kod bir makro içerir.

```cpp
DECODEPARM(CB_GETLBTEXT)
{
  P2WPOUT();

  P2LPOUTPTRSTR;
  P2IFDATA()
  {
    PARM(lpszBuffer, PPACK_STRINGORD, ED2);

    INDENT();

    P2IFISORD(lpszBuffer)
    {
      P2OUTORD(lpszBuffer);
    }
    else
    {
      PARM(lpszBuffer, LPTSTR, ED2);
      P2OUTS(lpszBuffer);
    }
  }
}
```

Makroların bu kodda olduğu gibi ağır kullanımı, kodun bakımını daha zor hale getirme eğilimi gösterir. Bu durumda, makrolar değişkenlerin bildirimlerini içerir. Makro, aşağıdaki gibi tanımlanır:

```cpp
#define PARM(var, type, src)type var = (type)src
```

Bu nedenle `lpszBuffer` değişkeni aynı işlevde iki kez bildirilmiştir. Bu, kodun makroları kullanmamasına (yalnızca ikinci tür bildirimini kaldırmanız) olanak tanıdığından, bu durum doğrudan düzeltilmek değildir. Olduğu gibi, makro kodunu sıradan kod olarak yeniden yazmak (sıkıcı ve olası hata durumunda olabilecek bir görev) veya uyarıyı devre dışı bırakma seçeneklerine talihsiz karar veririz.

Bu durumda, uyarıyı devre dışı bırakmayı kabul ediyoruz. Bunu aşağıdaki gibi bir pragma ekleyerek yapabiliriz:

```cpp
#pragma warning(disable : 4456)
```

Bir uyarıyı devre dışı bırakırken, bu durum yararlı bilgiler sağlayabileceğinden uyarının önleneceğini önlemek için, yalnızca uyarıyı üreten kod için devre dışı bırakma efektini kısıtlamak isteyebilirsiniz. Uyarıyı, onu oluşturan satırdan hemen sonra veya daha iyi bir makroya geri yüklemek için kod ekleyeceğiz. bu uyarı makroda gerçekleştiğinden, makrolarla çalışan **__pragma** anahtar sözcüğünü kullanın (`#pragma` makrolarda çalışmaz).

```cpp
#define PARM(var, type, src)__pragma(warning(disable : 4456))  \
type var = (type)src \
__pragma(warning(default : 4456))
```

Sonraki uyarı bazı kod düzeltmeleri gerektirir. Win32 API `GetVersion` (ve `GetVersionEx`) kullanım dışıdır.

```Output
warning C4996: 'GetVersion': was declared deprecated
```

Aşağıdaki kod, sürümünün nasıl elde edilir olduğunu gösterir.

```cpp
// check Windows version and set m_bIsWindows9x/m_bIsWindows4x/m_bIsWindows5x flags accordingly.
DWORD dwWindowsVersion = GetVersion();
```

Bu, Windows 95 ' de çalışıp çalışmadığını ve hangi Windows NT sürümünü kullandığınızı belirleyen dwWindowsVersion değerini inceleyen çok sayıda kod izler. Bu tarihten itibaren bu yana kodu kaldırdık ve bu değişkenlere yönelik tüm başvurularla ilgilentik.

[Windows 8.1 ve Windows Server 2012 R2 'Deki işletim sistemi sürümü değişiklikleri](/windows/win32/w8cookbook/operating-system-version-changes-in-windows-8-1) makalesinde durum açıklanır.

`CSpyApp` sınıfında, işletim sistemi sürümünü sorgulayan yöntemler vardır: `IsWindows9x`, `IsWindows4x`ve `IsWindows5x`. İyi bir başlangıç noktası, bu eski uygulama tarafından kullanılan teknolojiler açısından, desteklemeyi düşüntiğimiz Windows sürümlerinin (Windows 7 ve üzeri) Windows NT 5 ' e yakın olduğunu varsaymaktadır. Bu yöntemlerin kullanımları eski işletim sistemlerinin sınırlamalarıyla ilgilendi. Bu nedenle, bu yöntemleri `IsWindows5x` için TRUE, diğerleri için FALSE döndürecek şekilde değiştirdik.

```cpp
BOOL IsWindows9x() {/*return(m_bIsWindows9x);*/ return FALSE;  }
BOOL IsWindows4x() {/*return(m_bIsWindows4x);*/ return FALSE;  }
BOOL IsWindows5x() {/*return(m_bIsWindows5x);*/ return TRUE;  }
```

Yalnızca iç değişkenlerin doğrudan kullanıldığı birkaç yerde bırakılır. Bu değişkenleri kaldırdığımızdan, açıkça ele almanız gereken birkaç hata yaşıyoruz.

```Output
error C2065: 'm_bIsWindows9x': undeclared identifier
```

```cpp
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)
{
  pCmdUI->Enable(m_bIsWindows9x || hToolhelp32 != NULL);
}
```

Bunu bir yöntem çağrısıyla değiştirebiliriz veya doğru bir şekilde geçirmek ve Windows 9xiçin eski özel durumu kaldırmanız yeterlidir.

```cpp
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)
{
  pCmdUI->Enable(TRUE /*!m_bIsWindows9x || hToolhelp32 != NULL*/);
}
```

Varsayılan düzeydeki (3) son uyarının bitfield ile olması vardır.

```Output
treectl.cpp(1656): warning C4463: overflow; assigning 1 to bit-field that can only hold values from -1 to 0
```

Bunu tetikleyen kod aşağıdaki gibidir.

```cpp
m_bStdMouse = TRUE;
```

`m_bStdMouse` bildirimi, bir bitfield olduğunu gösterir.

```cpp
class CTreeListBox : public CListBox
{
  DECLARE_DYNCREATE(CTreeListBox)

  CTreeListBox();

  private:
  int ItemFromPoint(const CPoint& point);

  class CTreeCtl* m_pTree;
  BOOL m_bGotMouseDown : 1;
  BOOL m_bDeferedDeselection : 1;
  BOOL m_bStdMouse : 1;
```

Bu kod, yerleşik bool türü görselde C++desteklenmadan önce yazılmıştır. Bu tür kodda BOOL, **int**için bir **typedef** idi. **İnt** türü, **imzalı** bir türdür ve **imzalı bir int** 'in bit temsili, bir işaret biti olarak ilk biti kullanmaktır, bu nedenle int türünde bir bit alanından, büyük olasılıkla amaçlanan gibi değil 0 veya-1 temsil edilir.

Bu kodun Bitfields nedenleri olduğuna bakarak emin değilseniz. Nesne boyutunun küçük tutulması mi yoksa nesnenin ikili düzeninin kullanıldığı bir yerde mi var? Bitfield kullanımı için herhangi bir neden görmediğiniz için bunları sıradan BOOL üyelere değiştirdik. Bir nesnenin boyutunun küçük kalmasını sağlamak için bit alanları kullanımı, çalışma garantisi vermez. Derleyicinin türü nasıl yerleştireceğinize bağlıdır.

Bir **bool** standart türü kullanmanın yararlı olacağını merak ediyor olabilirsiniz. BOOL türü gibi eski kod desenlerinin birçoğu, daha sonra standart C++olarak çözülen sorunları çözmeye yönelik olarak kabul edildi, bu nedenle bool 'dan **bool** yerleşik türüne geçiş yapmak, kodunuzun ilk olarak yeni sürümde çalışmasını aldıktan sonra, yaptığınız değişikliğin yalnızca bir örneğidir.

Varsayılan düzeyde (düzey 3) görüntülenen tüm uyarılarla ilgilendikten sonra birkaç ek uyarıyı yakalamak için 4. düzey olarak değiştirdik. İlk görüntülenen aşağıdaki gibidir:

```Output
warning C4100: 'nTab': unreferenced formal parameter
```

Bu uyarıyı üreten kod aşağıdaki gibidir.

```cpp
virtual void OnSelectTab(int nTab) {};
```

Bu, yeterince zararsız görünmektedir, ancak `/W4` ve `/WX` ayarlanmış bir temiz derleme yaptığımız için, değişken adını öğrendiğimiz ve bu, okunabilirliği artırmak için dışarıda bıraktık.

```cpp
virtual void OnSelectTab(int /*nTab*/) {};
```

Aldığımız diğer uyarılar genel kod temizleme için yararlıdır. **İnt** veya **IŞARETSIZ int** 'ten sözcüğe ( **işaretsiz Short**için bir typedef olan) birkaç örtük dönüştürme vardır. Bunlar, olası veri kaybını içerir. Bu durumlarda WORD 'e bir atama ekledik.

Bu kod için aldığımız diğer 4. düzey uyarısı:

```Output
warning C4211: nonstandard extension used: redefined extern to static
```

Bu sorun, bir değişken ilk **extern**olarak bildirildiği ve daha sonra **statik**olarak bildirildiği zaman oluşur. Bu iki depolama sınıfı belirticinin anlamı birbirini dışlıyor, ancak buna Microsoft uzantısı olarak izin verilir. Kodun diğer derleyicilere taşınabilir olmasını istiyorsanız veya `/Za` (ANSI uyumluluğu) ile derlemek isterseniz, bildirimleri eşleşen depolama sınıfı belirticilerine sahip olacak şekilde değiştirirsiniz.

##  <a name="porting_to_unicode"></a>11. adım. MBCS 'den Unicode 'a taşıma

Windows dünyasında Unicode söylediğimizi, genellikle UTF-16 anlamına geldiğini unutmayın. Linux gibi diğer işletim sistemleri UTF-8 kullanır, ancak Windows genellikle değildir. MFC 'nin MBCS sürümü Visual Studio 2013 ve 2015 ' de kullanımdan kaldırılmıştır, ancak artık Visual Studio 2017 ' de kullanımdan kaldırılmıştır. Visual Studio 2013 veya 2015 kullanıyorsanız, bu adımı, başka bir iş yapmak veya zaman aşımı süresini uygun bir zamana kadar erteleyebilmek için, MBCS 'nin kullanım dışı olduğunu belirten, geçici olarak ortadan kaldırmak isteyebilir. Geçerli kod MBCS kullanır ve MFC 'nin ANSI/MBCS sürümünü yüklememiz gereken ile devam eder. Bunun yerine, büyük MFC kitaplığı, yükleme **ile C++**  varsayılan Visual Studio Desktop geliştirmenin bir parçası değildir, bu nedenle yükleyicideki isteğe bağlı bileşenlerden seçilmelidir. Bkz. [MFC MBCS dll eklentisi](../mfc/mfc-mbcs-dll-add-on.md). Bu özelliği indirerek ve Visual Studio 'yu yeniden başlattıktan sonra, MFC 'nin MBCS sürümünü derleyip bağlayabilirsiniz, ancak Visual Studio 2013 veya 2015 kullanıyorsanız MBCS hakkında uyarı almak için, proje özelliklerinin ön **işlemci** bölümünde veya *stffx. h* üstbilgi dosyasının veya diğer ortak üstbilgi dosyasının başlangıcında de önceden tanımlanmış makrolar listenize NO_WARN_MBCS_MFC_DEPRECATION eklemeniz gerekir.

Artık bazı bağlayıcı hatalarıyla karşılaştık.

```Output
fatal error LNK1181: cannot open input file 'mfc42d.lib'
```

LNK1181, bir MFC 'nin eski bir statik kitaplık sürümü bağlayıcı girdisine dahil edildiğinden oluşur. MFC 'yi dinamik olarak bağlayabilmemiz için bu gerekli değildir, bu nedenle yalnızca proje özelliklerinin **bağlayıcı** bölümündeki **GIRIŞ** özelliğinden tüm MFC statik kitaplıklarını kaldırmamız yeterlidir. Bu proje Ayrıca `/NODEFAULTLIB` seçeneğini de kullanıyor ve bunun yerine tüm kitaplık bağımlılıklarını listelemektedir.

```
msvcrtd.lib;msvcirtd.lib;kernel32.lib;user32.lib;gdi32.lib;advapi32.lib;Debug\SpyHk55.lib;%(AdditionalDependencies)
```

Şimdi eski çok baytlı karakter kümesi (MBCS) kodunu Unicode olarak güncelleştirmemize izin verin. Bu bir Windows uygulaması olduğundan, içkin Windows masaüstü platformu 'na bağlı olduğundan, Windows 'un kullandığı UTF-16 Unicode ' a bağlantı göndereceğiz. Platformlar arası kod yazıyorsanız veya bir Windows uygulamasını başka bir platforma taşırken, diğer işletim sistemlerinde yaygın olarak kullanılan UTF-8 ' e geçiş yapmayı düşünmek isteyebilirsiniz.

UTF-16 Unicode 'a taşıma seçeneği, yine de MBCS 'ye derleme yapmak isteyip istememize karar vermelidir.  MBCS 'yi destekleme seçeneğine sahip olmak istiyoruz, derleme sırasında \_MBCS veya \_UNICODE tanımlanıp tanımlanmayacağı ile ilgili olarak, **char** veya **wchar_t**çözümlenen karakter türü olarak TCHAR makrosunu kullanacağız. **Wchar_t** ve Ilişkili API 'leri yerine çeşitli API 'lerin TCHAR ve TCHAR sürümlerine geçiş yapmak, yalnızca \_UNICODE yerıne \_MBCS makrosunu tanımlayarak KODUNUZUN bir MBCS sürümüne geri dönebilirsiniz. TCHAR 'ın yanı sıra, yaygın olarak kullanılan typedefs, makrolar ve işlevler gibi çeşitli TCHAR sürümleri mevcuttur. Örneğin, LPCSTR yerine LPCTSTR ve bu şekilde devam eder. Proje Özellikleri iletişim kutusunda, **yapılandırma özellikleri**altında, **genel** bölümünde, **Unicode**karakter kümesini kullan ' ı kullanarak **karakter kümesi** özelliğini **kullanın** . Bu ayar, derleme sırasında önceden tanımlanan makroyu etkiler. Hem UNICODE makrosu hem de \_UNICODE makrosu vardır. Proje özelliği her ikisini de sürekli olarak etkiler. Windows üst bilgileri, MFC gibi C++ görsel üstbilgilerin Unicode \_kullanacağı Unicode kullanır, ancak biri tanımlandığında diğeri her zaman tanımlanır.

TCHAR 'dan UTF-16 Unicode 'a gitmek için iyi bir [kılavuz](/previous-versions/cc194801(v=msdn.10)) vardır. Bu yolu seçtik. İlk olarak, **karakter kümesi** özelliğini **Unicode karakter kümesini kullanacak** şekilde değiştiririz ve projeyi yeniden derliyoruz.

Koddaki bazı konumlar zaten, olasılığına, sonunda Unicode destekleyici olduğunu Görünüşe göre zaten TCHAR kullanıyor. Bazıları değildi. **Char için bir** **typedef** olan char örnekleri aradık ve bunların çoğunu TCHAR ile değiştirdi. Ayrıca, `sizeof(CHAR)`için baktık. CHAR 'dan TCHAR 'a her değiştirtiğimiz zaman, bu genellikle bir dizedeki karakter sayısını belirlemede kullanıldığından `sizeof(TCHAR)` olarak değişmemiz gerekiyordu. Burada yanlış tür kullanılması bir derleyici hatası oluşturmaz, bu nedenle bu durumda dikkat çekici bir değer ödemelidir.

Bu tür bir hata, yalnızca Unicode 'a geçiş sonrasında çok yaygındır.

```Output
error C2664: 'int wsprintfW(LPWSTR,LPCWSTR,...)': cannot convert argument 1 from 'CHAR [16]' to 'LPWSTR'
```

İşte bunu üreten kod örneği:

```cpp
wsprintf(szTmp, "%d.%2.2d.%4.4d", rmj, rmm, rup);
```

Hatayı kaldırmak için dize sabit değeri etrafında \_T yerleştiriyoruz.

```cpp
wsprintf(szTmp, _T("%d.%2.2d.%4.4d"), rmj, rmm, rup);
```

\_T makrosu, MBCS veya UNICODE ayarlarına bağlı olarak bir dize sabiti derlemesini bir **char** dize veya bir **wchar_t** dizesi olarak oluşturma efektinden oluşur. Tüm dizeleri Visual Studio 'daki \_T ile değiştirmek için, önce **hızlı değiştirme** (klavye: **CTRL**+**F**) kutusunu veya **dosyalardaki değiştir** (klavye: **CTRL**+**SHIFT**+**H**) öğesini açın, sonra **Normal ifadeleri kullan** onay kutusunu seçin. Arama metni olarak `((\".*?\")|('.+?'))` girin ve değiştirme metni olarak `_T($1)`. Bazı dizelerin etrafında \_T Makronuz zaten varsa, bu yordam onu tekrar ekler ve ayrıca, `#include`kullanırken olduğu gibi \_T **'yi kullanmak istemediğiniz** durumları da **bulabilir.**

Bu özel işlev olan [wsprintf](/windows/win32/api/winuser/nf-winuser-wsprintfw), aslında Windows üst bilgilerinde tanımlanmıştır ve bunun, olası arabellek taşmasından dolayı kullanılması tavsiye edilir. `szTmp` arabelleği için boyut verilmedi, bu nedenle işlevin, arabelleğe yazılacak tüm verileri tutabilmesini denetme yolu yoktur. Daha benzer sorunları giderdiğimiz güvenli CRT 'ye taşıma hakkında bir sonraki bölüme bakın. [_Stprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)ile değiştiriliyor.

Unicode 'a dönüştürme işleminde göreceğiniz diğer yaygın hata budur.

```Output
error C2440: '=': cannot convert from 'char *' to 'TCHAR *'
```

Bunu üreten kod aşağıdaki gibidir:

```cpp
pParentNode->m_szText = new char[strTitle.GetLength() + 1];
_tcscpy(pParentNode->m_szText, strTitle);
```

Bir dizeyi kopyalamak için TCHAR strcpy işlevi olan `_tcscpy` işlevi kullanılsa bile, ayrılan arabellek bir **char** tamponiydi. Bu, kolayca TCHAR olarak değiştirilmiştir.

```cpp
pParentNode->m_szText = new TCHAR[strTitle.GetLength() + 1];
_tcscpy(pParentNode->m_szText, strTitle);
```

Benzer şekilde, bir derleyici hatası ile garanti edildiğinde LPSTR (dize için uzun Işaretçi) ve LPCSTR (sabit dize için uzun işaretçi) ve LPCTSTR (uzun bir şekilde, sabit bir değer işaretçisi) olarak değiştiriliriz. Her durumun ayrı ayrı incelenmesi gerektiğinden, bu tür değişiklikleri genel arama ve değiştirme kullanarak yapamıyoruz. Bazı durumlarda, **bir** sonekine sahip Windows yapılarını kullanan bazı Windows iletilerini işlerken olduğu gibi, **char** sürümü de bulunur. Windows API 'sinde, soneki **BIR** ASCII veya ANSI anlamına gelir (ve ayrıca MBCS için geçerlidir) ve **W** SONEKI geniş karakter veya UTF-16 Unicode anlamına gelir. Bu adlandırma deseninin Windows üst bilgilerinde kullanılması, ancak yalnızca bir MBCS sürümünde önceden tanımlanmış bir işlevin Unicode sürümünü eklememiz gerektiğinde Spy + + kodunda de izlenir.

Bazı durumlarda, bir türü, doğru bir şekilde çözümlenen bir sürümü (örneğin, WNDCLASSA yerine) kullanarak değiştirmek zorunda kaldık.

Çoğu durumda, `GetClassName` gibi bir Win32 API (`GetClassNameA`) genel sürümünü (makro) kullanmak zorunda kaldık. İleti işleyici anahtarı ifadesinde, bazı iletiler MBCS veya Unicode 'a özeldir, bu durumda genel olarak adlandırılmış işlevleri ve **w** 'a özgü işlevleri değiştirdiğimiz **ve genel** ad için, UNICODE 'un tanımlanıp tanımlanmayacağı konusunda doğru **a** veya **w** adına çözümlenen bir makro eklediği için, bu durumlarda kodu değiştirmek zorunda kaldık.  Kodun birçok bölümünde, UNICODE \_tanımlamak için geçiş yaptığımız sırada W sürümü, **bir** sürüm istenen gibi olduğunda bile seçilir.

Özel eylemlerin alınması gereken birkaç yer vardır. `WideCharToMultiByte` veya `MultiByteToWideChar` herhangi bir kullanımı daha yakından bir görünüm gerektirebilir. İşte `WideCharToMultiByte` kullanıldığı bir örnek.

```cpp
BOOL C3dDialogTemplate::GetFont(CString& strFace, WORD& nFontSize)
{
  ASSERT(m_hTemplate != NULL);

  DLGTEMPLATE* pTemplate = (DLGTEMPLATE*)GlobalLock(m_hTemplate);
  if ((pTemplate->style & DS_SETFONT) == 0)
  {
    GlobalUnlock(m_hTemplate);
    return FALSE;
  }

  BYTE* pb = GetFontSizeField(pTemplate);
  nFontSize = *(WORD*)pb;
  pb += sizeof (WORD);
  WideCharToMultiByte(CP_ACP, 0, (LPCWSTR)pb, -1,
  strFace.GetBufferSetLength(LF_FACESIZE), LF_FACESIZE, NULL, NULL);
  strFace.ReleaseBuffer();
  GlobalUnlock(m_hTemplate);
  return TRUE;
}
```

Bunu çözmek için, bunun yapıldığı nedenin bir `strFace``CString`iç arabelleğine bir yazı tipinin adını temsil eden geniş bir karakter dizesi kopyalamanın was olduğunu anladık. Bu, çok baytlı `CString` dizeleri için geniş karakter `CString` dizeleri gibi biraz farklı kod gerektirdiğinden bu durumda bir `#ifdef` ekledik.

```cpp
#ifdef _MBCS
WideCharToMultiByte(CP_ACP, 0, (LPCWSTR)pb, -1,
strFace.GetBufferSetLength(LF_FACESIZE), LF_FACESIZE, NULL, NULL);
strFace.ReleaseBuffer();
#else
wcscpy(strFace.GetBufferSetLength(LF_FACESIZE), (LPCWSTR)pb);
strFace.ReleaseBuffer();
#endif
```

Kuşkusuz `wcscpy` bunun yerine, gerçekten de daha güvenli sürümü `wcscpy_s`kullandık. Sonraki bölümde bu ele alınmaktadır.

Çalışmamıza bir denetim olarak, **karakter kümesini** **çok baytlı karakter kümesini kullanacak** şekilde sıfırlamamız ve kodun hala MBCS 'yi ve Unicode 'u kullanarak derlendiğinden emin olması gerekir. Daha az söylemek gerekir, tüm bu değişiklikler sonrasında yeniden derlenen uygulamada tam bir test geçişi yürütülmelidir.

Bu Spy + + çözümü ile çalışımızda, ortalama C++ bir geliştiricinin kodu Unicode 'a dönüştürmesi için iki çalışma günü yaklaşık olarak gerçekleşmelidir. Yeniden test süresini içermiyordu.

##  <a name="porting_to_secure_crt"></a>12. adım. Güvenli CRT kullanmak için taşıma

CRT işlevlerinin güvenli sürümlerini ( **_s** son eki olan sürümler) kullanmak üzere kodun taşıma işlemi bir sonraki seçenektir. Bu durumda genel strateji, işlevi **_s** sürümüyle değiştirmek ve genellikle gerekli ek arabellek boyutu parametrelerini eklemektir. Çoğu durumda bu, boyut bilindiğinden basittir. Diğer durumlarda, boyutun hemen kullanılamadığı yerde, CRT işlevini kullanan işleve ek parametreler eklemek veya belki de hedef arabelleğin kullanımını inceleyerek uygun boyut sınırlarının ne olduğunu görmeniz gerekir.

Visual C++ , çok sayıda boyut parametresi eklemeden ve şablon aşırı yüklerini kullanarak kodu güvenli hale getirmeye daha kolay bir hale getirmek için bir el sağlar. Bu aşırı yüklemeler şablonlar olduğundan, yalnızca olarak C++derlerken kullanılabilir, c. Spyxxhk bir c projem olduğundan, bu, BT bu şekilde çalışmaz.  Ancak, spyxx değildir ve elyi kullanabiliriz. Bu, aşağıdaki gibi bir satırı, projenin her dosyasında Derlenecek bir yerde (örneğin, stbafx. h içinde) eklemek için kullanılır:

```cpp
#define _CRT_SECURE_TEMPLATE_OVERLOADS 1
```

Bunu tanımlarken, bir ham işaretçi yerine arabellek bir dizi olduğunda, bu boyut dizi türünden algılanır ve bu, size sağlamak zorunda kalmadan boyut parametresi olarak kullanılır. Bu, kodu yeniden yazma karmaşıklığını kesmeye yardımcı olur. İşlev adını **_s** sürümle değiştirmeniz gerekir, ancak bu, genellikle bir arama ve değiştirme işlemi tarafından yapılabilir.

Bazı işlevlerin dönüş değerleri değişti. Örneğin, `_itoa_s` (ve `_itow_s` ve makro `_itot_s`), dize yerine bir hata kodu (`errno_t`) döndürür. Bu şekilde, bu durumda `_itoa_s` çağrısını ayrı bir satıra taşımanız ve arabelleğin tanımlayıcısıyla değiştirmeniz gerekir.

Yaygın durumlardan bazıları: `memcpy`için, `memcpy_s`geçiş yaparken sıklıkla kopyalandığı yapının boyutunu ekledik. Benzer şekilde, çoğu dize ve arabellek için, dizi veya arabelleğin boyutu, arabelleğin bildiriminden veya arabelleğin ilk olarak ayrıldığı yeri bularak kolayca belirlenir. Bazı durumlarda, arabelleğin büyük bir kısmının gerçekten kullanılabilir olduğunu belirlemeniz gerekir ve bu bilgiler değiştirmekte olduğunuz işlevin kapsamında yoksa, ek bir parametre olarak eklenmelidir ve çağıran kodun şu şekilde değiştirilmesi gerekir bilgileri sağlayın.

Bu teknikler sayesinde, kodun güvenli CRT işlevlerini kullanmak için bir gün boyunca dönüştürülmesi gerekir. Şablon aşırı yüklerini seçip boyut parametrelerini el ile eklemek istiyorsanız, büyük olasılıkla iki kez daha zaman alabilir.

##  <a name="deprecated_forscope"></a>13. adım. /Zc: forScope-kullanım dışı

Visual C++ 6,0 ' den bu yana derleyici, bir döngüde belirtilen değişkenlerin kapsamını döngünün kapsamına göre sınırlayan geçerli standarda uyar. [/Zc: forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) derleyici seçeneği (proje özelliklerindeki**döngü kapsamı için uygunluğu zorla** ), bunun hata olarak raporlanıp raporlanmadığını denetler. Kodumuzu uyumlu olacak şekilde güncelleştirmemiz ve yalnızca döngünün dışında bildirimler ekleyeceğiz. Kod değişikliği yapmaktan kaçınmak için, C++ proje özelliklerinin **dil** bölümündeki bu ayarı `No (/Zc:forScope-)`olarak değiştirebilirsiniz. Ancak, `/Zc:forScope-` bir görselin C++gelecekteki bir sürümünde kaldırılabileceğini aklınızda bulundurun. bu nedenle, kodunuzun standart ile uyumlu olacak şekilde değiştirilmesi gerekir.

Bu sorunların düzeltilmesi nispeten kolaydır, ancak kodunuza bağlı olarak çok sayıda kodu etkileyebilir. Tipik bir sorun aşağıda verilmiştir.

```cpp
int CPerfTextDataBase::NumStrings(LPCTSTR mszStrings) const
{
  for (int n = 0; mszStrings[0] != 0; n++)
  mszStrings = _tcschr(mszStrings, 0) + 1;
  return(n);
}
```

Yukarıdaki kod şu hatayı üretir:

```Output
'n': undeclared identifier
```

Bu durum, derleyici artık C++ standart ile uyumlu olmayan koda izin veren bir derleyici seçeneğinin kullanım dışı bırakıldığı için oluşur. Standart olarak, bir döngü içindeki bir değişkeni bildirmek, kapsamını yalnızca döngüyle kısıtlar, bu nedenle döngünün dışında bir döngü sayacı kullanmanın yaygın bir yöntemi, aşağıdaki düzeltilen kodda olduğu gibi, sayaç bildiriminin aynı zamanda döngü dışına taşınmasını gerektirir :

```cpp
int CPerfTextDataBase::NumStrings(LPCTSTR mszStrings) const
{
  int n;
  for (n = 0; mszStrings[0] != 0; n++)
  mszStrings = _tcschr(mszStrings, 0) + 1;
  return(n);
}
```

## <a name="summary"></a>Özet

Özgün Visual C++ 6,0 kodundan en son derleyiciye yönelik Spy + + ' a taşıma, yaklaşık bir hafta boyunca yaklaşık 20 saatlik kodlama süresi sürdü. Visual Studio 6,0 ' den Visual Studio 2015 ' ye kadar ürünün sekiz yayımlarından doğrudan yükseltiyoruz. Bu artık, projelerde büyük ve küçük olan tüm yükseltmelerde önerilen yaklaşımdır.

## <a name="see-also"></a>Ayrıca bkz.

[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Önceki örnek olay incelemesi: COM Spy](../porting/porting-guide-com-spy.md)
