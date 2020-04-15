---
title: 'Taşıma Kılavuzu: Spy++'
ms.date: 10/23/2019
ms.assetid: e558f759-3017-48a7-95a9-b5b779d5e51d
ms.openlocfilehash: edccf18c3fbc4d6eeec2ed0aa59df0e7d1f85335
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353376"
---
# <a name="porting-guide-spy"></a>Taşıma Kılavuzu: Spy++

Bu taşıma lı örnek olay incelemesi, tipik bir taşıma projesinin nasıl olduğu, karşılaşabileceğiniz sorun türleri ve taşıma sorunlarını ele almak için bazı genel ipuçları ve püf noktaları hakkında bir fikir vermek üzere tasarlanmıştır. Bir projeyi taşıma deneyimi kodun özelliklerine çok bağlı olduğundan, taşıma için kesin bir kılavuz olması amaçlanmaz.

## <a name="spy"></a>Spy++

Spy++, Windows masaüstündeki kullanıcı arabirimi öğeleri hakkında her türlü bilgi sağlayan Windows masaüstü için yaygın olarak kullanılan bir GUI tanı aracıdır. Pencerelerin tam hiyerarşisini gösterir ve her pencere ve denetim le ilgili meta verilere erişim sağlar. Bu yararlı uygulama uzun yıllar Visual Studio ile sevk edilmiştir. En son Visual C++ 6.0'da derlenen ve Visual Studio 2015'e taşınan eski bir versiyonunu bulduk. Visual Studio 2017 veya Visual Studio 2019 deneyimi hemen hemen aynı olmalıdır.

Bu servis talebinin, Özellikle Visual C++ 6.0'dan beri her sürümüyle güncelleştirilmeyen eski projeler de, MFC ve Win32 API kullanan Windows masaüstü uygulamalarını taşıması için tipik olduğunu kabul ettik.

## <a name="step-1-converting-the-project-file"></a><a name="convert_project_file"></a>Adım 1. Proje dosyasını dönüştürme.

Visual C++ 6.0'ın iki eski .dsw dosyası olan proje dosyası, daha fazla dikkat gerektiren hiçbir sorun olmadan kolayca dönüştürülür. Bir proje Spy++ uygulamasıdır. Diğer SpyHk, C, destekleyici bir DLL yazılmış. Daha karmaşık [projeler, burada](../porting/visual-cpp-porting-and-upgrading-guide.md)tartışıldığı gibi kolayca yükseltme olmayabilir.

İki projeyi yükselttikten sonra çözümümüz şu şekilde göründü:

![Spy&#43;&#43; Çözüm](../porting/media/spyxxsolution.PNG "Spy&#43;&#43; Çözüm")

İki projemiz var, biri çok sayıda C++ dosyasına sahip, diğeri de C ile yazılmış bir DLL.

## <a name="step-2-header-file-problems"></a><a name="header_file_problems"></a>Adım 2. Üstbilgi dosyası sorunları

Yeni dönüştürülmüş bir proje inşa edildikten sonra, sık sık bulacağınız ilk şeylerden biri, projenizin kullandığı üstbilgi dosyalarının bulunamayan olmasıdır.

Spy++'da bulunamayan dosyalardan biri verstamp.h idi. Bir internet aramasından, bunun eski bir veri teknolojisi olan DAO SDK'dan geldiğini belirledik. Bu üstbilgi dosyasından hangi sembollerin kullanıldığını öğrenmek, bu dosyaya gerçekten gerek ipte olmadığını veya bu sembollerin başka bir yerde tanımlanıp tanımlanmadığını görmek istedik, bu nedenle üstbilgi dosyası bildirimini yorumladık ve yeniden derledik. Bu gerekli olan sadece bir sembol, VER_FILEFLAGSMASK çıkıyor.

```Output
1>C:\Program Files (x86)\Windows Kits\8.1\Include\shared\common.ver(212): error RC2104: undefined keyword or key name: VER_FILEFLAGSMASK
```

Mevcut dosyalarda bir sembol bulmanın en kolay yolu **Dosyalarda Bul** **(Ctrl**+**Shift**+**F)** kullanmak ve Visual **C++ Include Directories 'i**belirtmektir. Ntverp.h'de bulduk. Biz verstamp.h ntverp.h ile dahil değiştirildi ve bu hata kayboldu.

## <a name="step-3-linker-outputfile-setting"></a><a name="linker_output_settings"></a>Adım 3. Linker OutputFile ayarı

Eski projelerde bazen, yükseltmeden sonra sorunlara neden olabilecek alışılmadık konumlara yerleştirilen dosyalar bulunur. Bu durumda, Visual Studio'nun proje klasörlerinden birinde değil, oraya yerleştirilen bazı üstbilgi dosyalarını bulabilmesi için proje özelliklerine `$(SolutionDir)` **Ekle** yoluna eklememiz gerekir.

MSBuild, **Link.OutputFile** özelliğinin **TargetPath** ve **TargetName** değerleriyle eşleşmeyinve MSB8012'yi veren şikayette bulundu.

```Output
warning MSB8012: TargetPath(...\spyxx\spyxxhk\.\..\Debug\SpyxxHk.dll) does not match the Linker's OutputFile property value (...\spyxx\Debug\SpyHk55.dll). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).warning MSB8012: TargetName(SpyxxHk) does not match the Linker's OutputFile property value (SpyHk55). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).
```

**Link.OutputFile** yapı çıktısýr (EXE, DLL, örneğin) ve `$(TargetDir)$(TargetName)$(TargetExt)`normalde yol, dosya adý ve uzantı saýnýrý veren yapýlýr. Bu, projeleri eski Visual C++ yapı aracından (vcbuild.exe) yeni yapı aracına (MSBuild.exe) geçirdiğinizde sık karşılaşılan bir hatadır. Yapı aracı değişikliği Visual Studio 2010'da meydana geldiğinden, 2010 öncesi bir projeyi 2010 veya daha sonraki bir sürüme geçirdiğinizde bu sorunla karşılaşabilirsiniz. Temel sorun, proje geçiş sihirbazı, değerinin diğer proje ayarlarına göre ne olması gerektiğini belirlemek her zaman mümkün **olmadığından, Bağlantı.OutputFile** değerini güncelleştirmemesidir. Bu nedenle, genellikle el ile ayarlamanız gerekir. Daha fazla bilgi için Visual C++ blogundaki bu [gönderiye](https://devblogs.microsoft.com/cppblog/visual-studio-2010-c-project-upgrade-guide/) bakın.

Bu durumda, dönüştürülen projedeki **Link.OutputFile** özelliği yapılandırmaya bağlı olarak Spy++ projesi için .\Debug\Spyxx.exe ve .\Release\Spyxx.exe olarak ayarlanmıştır. En iyi bahis sadece **tüm yapılandırmaları** `$(TargetDir)$(TargetName)$(TargetExt)` için bu hardcoded değerleri değiştirmektir. Bu işe yaramazsa, buradan özelleştirebilir veya bu değerlerin ayarlandığı **Genel** bölümdeki özellikleri değiştirebilirsiniz (özellikler **Çıktı Dizini,** **Hedef Adı**ve **Hedef Uzantısı'dır.** Görüntülediğiniz özellik makrokullanıyorsa, yapılan makro ikameleriyle son dizeyi gösteren bir iletişim kutusunu getirmek için açılır listede **Edit'i** seçebileceğinizi unutmayın. **Makrolar** düğmesini seçerek kullanılabilir tüm makroları ve bunların geçerli değerlerini görüntüleyebilirsiniz.

## <a name="step-4-updating-the-target-windows-version"></a><a name="updating_winver"></a>Adım 4. Hedef Windows Sürümünü Güncelleştirme

Sonraki hata, WINVER sürümünün artık MFC'de desteklenmediğini gösterir. Windows XP için WINVER 0x0501'dir.

```Output
C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxv_w32.h(40): fatal error C1189: #error:  MFC does not support WINVER less than 0x0501.  Please change the definition of WINVER in your project properties or precompiled header.
```

Windows XP artık Microsoft tarafından desteklenmemektedir, bu nedenle Visual Studio'da hedeflemeye izin verilse bile, uygulamalarınızda bunun desteğini phasing ve kullanıcılarınızı Windows'un yeni sürümlerini benimsemeye teşvik etmelidir.

Hatadan kurtulmak için, **Project Properties** ayarını şu anda hedeflemek istediğiniz Windows'un en düşük sürümüne güncelleyerek WINVER'i tanımlayın. [Burada](/windows/win32/WinProg/using-the-windows-headers)çeşitli Windows sürümleri için değerler tablosu bulun.

*Stdafx.h* dosyası bu makro tanımlarından bazılarını içeriyordu.

```cpp
#define WINVER       0x0500  // these defines are set so that we get the
#define _WIN32_WINNT 0x0500  // maximum set of message/flag definitions,
#define _WIN32_IE    0x0400  // from both winuser.h and commctrl.h.
```

WINVER biz Windows 7 olarak ayarlayacak. Değeri (0x0601) yerine Windows 7 (_WIN32_WINNT_WIN7) için makroyu kullanırsanız kodu daha sonra okumak daha kolaydır.

```cpp
#define WINVER _WINNT_WIN32_WIN7 // Minimum targeted Windows version is Windows 7
```

## <a name="step-5-linker-errors"></a><a name="linker_errors"></a>Adım 5. Bağlayıcı Hataları

Bu değişikliklerle, SpyHk (DLL) projesi oluşturur ancak bir bağlayıcı hatası üretir.

```Output
LINK : warning LNK4216: Exported entry point _DLLEntryPoint@12
```

Bir DLL için giriş noktası dışa aktarılmamalıdır. Giriş noktası yalnızca DLL belleğe ilk yüklendiğinde yükleyici tarafından çağrılacak şekilde tasarlanmıştır, bu nedenle diğer arayanlar için olan dışa aktarma tablosunda olmamalıdır. Sadece **__declspec (dllexport)** direktifinin bağlı olmadığından emin olmalıyız. Spyxxhk.c olarak, biz iki yerden kaldırmak zorunda, beyan `DLLEntryPoint`ve tanımı . Bu yönergeyi kullanmak hiçbir zaman mantıklı olmamıştır, ancak bağlayıcı ve derleyicinin önceki sürümleri sorun olarak işaretlemedi. Bağlayıcının yeni sürümleri bir uyarı verir.

```cpp
// deleted __declspec(dllexport)
BOOL WINAPI DLLEntryPoint(HINSTANCE hinstDLL,DWORD fdwReason, LPVOID lpvReserved);
```

C DLL projesi, SpyHK.dll, şimdi oluşturur ve hatasız bağlantılar.

## <a name="step-6-more-outdated-header-files"></a><a name="outdated_header_files"></a>Adım 6. Daha eski üstbilgi dosyaları

Bu noktada biz ana yürütülebilir proje, Spyxx üzerinde çalışmaya başlar.

Diğer birkaç dosya bulunamadı: ctl3d.h ve penwin.h. Üstbilginin neler olduğunu belirlemek için Internet'te arama yapmak yararlı olabilir, ancak bazen bilgiler bu kadar yararlı değildir. Ctl3d.h'nin Exchange Development Kit'in bir parçası olduğunu ve Windows 95'te belirli bir denetim stili için destek sağladığını ve penwin.h'nin eski bir API olan Window Pen Computing ile ilgili olduğunu öğrendik. Bu durumda, biz sadece `#include` satır dışarı yorum ve verstamp.h ile yaptığı gibi tanımsız semboller ile anlaşma. 3B Denetimler veya Kalem Bilgi İşlem ile ilgili her şey projeden kaldırıldı.

Yavaş yavaş ortadan kaldırdığınız birçok derleme hatası olan bir proje göz önüne alındığında, `#include` yönergeyi kaldırdığınızda eski bir API'nin tüm kullanımlarını hemen bulmak gerçekçi değildir. Biz hemen tespit etmedi, ama daha sonra bir noktada WM_DLGBORDER tanımsız olduğu bir hata geldi. Aslında ctl3d.h gelen sadece bir çok tanımlanmamış semboller. Eski bir API ile ilişkili olduğunu belirledikten sonra, koddaki tüm başvuruları kaldırdık.

## <a name="step-7-updating-old-iostreams-code"></a><a name="updating_iostreams_code"></a>Adım 7. Eski iostreams kodunu güncelleştirme

Sonraki hata iostreams kullanan eski C++ kodu ile yaygındır.

```Output
mstream.h(40): fatal error C1083: Cannot open include file: 'iostream.h': No such file or directory
```

Sorun, eski iostreams kitaplığı kaldırıldı ve değiştirildi. Eski iostream'leri yeni standartlarla değiştirmeliyiz.

```cpp
#include <iostream.h>
#include <strstrea.h>
#include <iomanip.h>
```

Bunlar güncelleştirilmiş içerir:

```cpp
#include <iostream>
#include <sstream>
#include <iomanip>
```

Bu değişiklikle, `ostrstream`artık kullanılmayan sorunlarla karşı larımız var. Uygun değiştirme ostringstream olduğunu. Kodu çok fazla değiştirmemek için `ostrstream` en azından başlangıç olarak bir **typedef** eklemeyi deneriz.

```cpp
typedef std::basic_ostringstream<TCHAR> ostrstream;
```

Şu anda proje MBCS (Multi-bayt Karakter Kümesi) kullanılarak oluşturulur, bu nedenle **char** uygun karakter veri türüdür. Ancak, kodu UTF-16 Unicode için daha kolay bir güncelleştirmeye izin vermek için, proje ayarlarındaki **Karakter Kümesi** özelliğinin MBCS veya Unicode olarak ayarlanıp ayarlanmadığına bağlı olarak bu durumu **char** veya **wchar_t** olarak günceller. `TCHAR`

Birkaç kod parçasının güncelleştirilmesi gerekir.  Biz taban sınıf `ios` yerine `ios_base`, ve biz ostream\<yerine basic_ostream T> gereğidir. Biz iki ek typedefs ekleyin ve bu bölümü derler.

```cpp
typedef std::basic_ostream<TCHAR> ostream;
typedef ios_base ios;
```

Bu typedefs kullanarak sadece geçici bir çözümdür. Daha kalıcı bir çözüm için, her başvuruyu yeniden adlandırılmış veya eski API'ye güncelleyebiliriz.

Bir sonraki hata burada.

```Output
error C2039: 'freeze': is not a member of 'std::basic_stringbuf<char,std::char_traits<char>,std::allocator<char>>'
```

Bir sonraki sorun, `basic_stringbuf` bir `freeze` yöntem yok. Yöntem `freeze` eski `ostream`bir bellek sızıntısını önlemek için kullanılır. Yeniyi `ostringstream`kullandığımıza göre buna ihtiyacımız yok. Aramayı `freeze`silebiliriz.

```cpp
//rdbuf()->freeze(0);
```

Sonraki iki hata bitişik satırlarda oluştu. İlk kullanma `ends`hakkında şikayet , hangi `iostream` bir dize için null terminator ekler eski kütüphanenin IO manipülatör. Bu hatalardan ikincisi, `str` yöntemin çıktısının const olmayan bir işaretçiye atayamaması gerektiğini açıklar.

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

Dize her zaman `ends` null-sonlandırılır, böylece satır kaldırılabilir, yeni akış kitaplığı kullanarak gerekli değildir. İkinci sorun için, sorun şimdi `str()` bir dize için karakter dizisine bir işaretçi döndürmez; türünü döndürür. `std::string` İkinci çözüm türü değiştirmek `LPCSTR` ve işaretçi istemek `c_str()` için yöntemi kullanmaktır.

```cpp
//*this << ends;
LPCTSTR psz = str().c_str();
```

Bu kodda bir süre kafamızı karıştıran bir hata oluştu.

```cpp
MOUT << _T(" chUser:'") << chUser
<< _T("' (") << (INT)(UCHAR)chUser << _T(')');
```

Makro MOUT türünden `*g_pmout` `mstream`bir nesne olan giderir. Sınıf `mstream` standart çıktı string sınıfından `std::basic_ostream<TCHAR>`türetilmiştir. Ancak \_Unicode'a dönüştürmeye hazırlandığımız dize etrafındaki T ile operatör ** <<** için aşırı yük çözünürlüğü aşağıdaki hata iletisiyle başarısız olur:

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

Tanımları <<o kadar çok **operatör** vardır ki, bu tür hatalar korkutucu olabilir. Mevcut aşırı yüklere daha yakından baktıktan sonra, çoğunun alakasız olduğunu görebiliriz ve sınıf `mstream` tanımına daha yakından bakarak, bu durumda çağrılması gerektiğini düşündüğümüz aşağıdaki işlevi belirledik.

```cpp
mstream& operator<<(LPTSTR psz)
{
  return (mstream&)ostrstream::operator<<(psz);
}
```

Çağrılmamasının nedeni, dize literal'in, `const wchar_t[10]` o uzun hata iletisinin son satırından görebileceğiniz şekilde türe sahip olmasıdır, bu nedenle const olmayan bir işaretçiye dönüştürme otomatik değildir. Ancak bu işleç giriş parametresini değiştirmemelidir, bu nedenle `LPCTSTR` `const char*` daha uygun parametre türü `const wchar_t*` (MBCS ve `LPTSTR` `char*` Unicode olarak derlenirken) (MBCS olarak ve Unicode olarak) değil( MBCS olarak ve `wchar_t*` Unicode olarak) değildir. Bu değişikliği yapmak bu hatayı giderir.

Bu tür dönüştürme eski, daha az sıkı derleyici altında izin verildi, ancak daha yeni uyumluluk değişiklikleri daha doğru kod gerektirir.

## <a name="step-8-the-compilers-more-strict-conversions"></a><a name="stricter_conversions"></a>Adım 8. Derleyicinin daha katı dönüşümleri

Biz de aşağıdaki gibi birçok hata olsun:

```Output
error C2440: 'static_cast': cannot convert from 'UINT (__thiscall CHotLinkCtrl::* )(CPoint)' to 'LRESULT (__thiscall CWnd::* )(CPoint)'
```

Hata, yalnızca bir makro olan bir ileti haritasında oluşur:

```cpp
BEGIN_MESSAGE_MAP(CFindToolIcon, CWnd)
// other messages omitted...
ON_WM_NCHITTEST() // Error occurs on this line.
END_MESSAGE_MAP()
```

Bu makronun tanımına baktığımızda, işlevine `OnNcHitTest`atıfta bulunulmasını görüyoruz.

```cpp
#define ON_WM_NCHITTEST() \
{ WM_NCHITTEST, 0, 0, 0, AfxSig_l_p, \
(AFX_PMSG)(AFX_PMSGW) \
(static_cast< LRESULT (AFX_MSG_CALL CWnd::*)(CPoint) > (&ThisClass :: OnNcHitTest)) },
```

Sorun, üye işlev türlerine işaretçideki uyumsuzlukla ilgilidir. Bu, türetilmiş bir `CHotLinkCtrl` taban dönüştürme `CWnd` olduğundan, sorun sınıf türü olarak sınıf türünden sınıf türüne dönüştürme değildir. Sorun dönüş türüdür: UINT vs LRESULT. LRESULT, hedef ikili türüne bağlı olarak 64 bit işaretçi veya 32 bit işaretçi olan LONG_PTR çözer, bu nedenle UINT bu türe dönüştürmez. Birçok ileti eşlemi yönteminin dönüş türü 64 bit uyumluluk değişikliklerinin bir parçası olarak Visual Studio 2005'te UINT'ten LRESULT'a değiştiğinden, 2005'ten önce yazılan kodu yükseltmede bu durum nadir değildir. İade türünü Aşağıdaki koddaki UINT'den LRESULT olarak değiştiriyoruz:

```cpp
afx_msg UINT OnNcHitTest(CPoint point);
```

Değişiklikten sonra aşağıdaki kodu var:

```cpp
afx_msg LRESULT OnNcHitTest(CPoint point);
```

CWnd'den türetilen farklı sınıflarda bu işlevin yaklaşık on oluşumu olduğundan, imleç bunları bulmak ve **Bunları Bul Simgesi** araç penceresinden onlara gitmek için düzenleyicideki işlevde yken **Tanıma (Klavye:** **F12)** git ve **Bildirime Git** 'i (Klavye: **Ctrl**+**F12)** kullanmak yararlıdır. **Tanım'a git** genellikle ikisinin daha kullanışlıdır. **Bildirime git,** arkadaş sınıfı bildirimleri veya ileri başvurular gibi tanımlayıcı sınıf bildirimi dışındaki bildirimleri bulur.

## <a name="step-9-mfc-changes"></a><a name="mfc_changes"></a>Adım 9. MFC Değişiklikleri

Sonraki hata da değiştirilmiş bir bildirim türü ile ilgilidir ve aynı zamanda bir makro oluşur.

```Output
error C2440: 'static_cast': cannot convert from 'void (__thiscall CFindWindowDlg::* )(BOOL,HTASK)' to 'void (__thiscall CWnd::* )(BOOL,DWORD)'
```

Sorun, ikinci parametrenin `CWnd::OnActivateApp` HTASK'tan DWORD'e değişmesidir. Bu değişiklik Visual Studio, Visual Studio .NET'in 2002 sürümünde meydana geldi.

```cpp
afx_msg void OnActivateApp(BOOL bActive, HTASK hTask);
```

OnActivateApp'ın türetilmiş sınıflardaki beyanlarını aşağıdaki gibi güncellememiz gerekir:

```cpp
afx_msg void OnActivateApp(BOOL bActive, DWORD dwThreadId);
```

Bu noktada projeyi derleyebiliyoruz. Ancak üzerinde çalışım gereken bir kaç uyarı var ve yükseltmenin MBCS' den Unicode' a düşünme veya Secure CRT fonksiyonlarını kullanarak güvenliği artırmak gibi isteğe bağlı bölümleri de var.

## <a name="step-10-addressing-compiler-warnings"></a><a name="compiler_warnings"></a>Adım 10. Derleyici uyarılarının ele alınması

Uyarıların tam listesini almak için, yalnızca geçerli derlemeden uyarı raporları aldığınızdan, daha önce derlenen her şeyin yeniden derleneceğinden emin olmak için, sıradan bir yapı yerine çözüm üzerinde **Yeniden Oluştur'u** yapmanız gerekir. Diğer soru, geçerli uyarı düzeyini kabul etmek mi yoksa daha yüksek bir uyarı düzeyi mi kullanacağımdır.  Çok sayıda kod taşırken, özellikle eski kod, daha yüksek bir uyarı düzeyi kullanmak uygun olabilir.  Ayrıca varsayılan uyarı düzeyi ile başlamak ve sonra tüm uyarıları almak için uyarı düzeyini artırmak isteyebilirsiniz. `/Wall`Kullanırsanız, sistem üstbilgi dosyalarında bazı uyarılar almak, `/W4` bu yüzden birçok kişi sistem üstbilgi için uyarılar almadan kendi kodu üzerinde en çok uyarı almak için kullanın. Uyarıların hata olarak gösterilmesini `/WX` istiyorsanız, seçeneği ekleyin. Bu **ayarlar, Project Properties** iletişim kutusunun **C/C++** bölümünde yer almaktadır.

Sınıftaki `CSpyApp` yöntemlerden biri, artık desteklenmeyen bir işlev hakkında bir uyarı üretir.

```cpp
void SetDialogBkColor() {CWinApp::SetDialogBkColor(::GetSysColor(COLOR_BTNFACE));}
```

Uyarı aşağıdaki gibidir.

```Output
warning C4996: 'CWinApp::SetDialogBkColor': CWinApp::SetDialogBkColor is no longer supported. Instead, handle WM_CTLCOLORDLG in your dialog
```

WM_CTLCOLORDLG ileti zaten Spy++ kodunda işlendi, bu nedenle gerekli `SetDialogBkColor`tek değişiklik artık gerekli olan herhangi bir başvuruyu silmekoldu.

Bir sonraki uyarı değişken adı dışarı yorumlayarak düzeltmek için basitoldu. Biz aşağıdaki uyarı aldı:

```Output
warning C4456: declaration of 'lpszBuffer' hides previous local declaration
```

Bunu oluşturan kod bir makro içerir.

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

Bu kodda olduğu gibi makroların yoğun kullanımı, kodun korunmasını zorlaştırır. Bu durumda, makrolar değişkenlerin bildirimlerini içerir. Makro PARM aşağıdaki gibi tanımlanır:

```cpp
#define PARM(var, type, src)type var = (type)src
```

Bu `lpszBuffer` nedenle değişken aynı işlevde iki kez bildirilir. Kod makrolar (sadece ikinci tür bildirimini kaldırmak) kullanmıyorsanız olurdu gibi bu düzeltmek için basit değil. Olduğu gibi, makro kodunu sıradan kod (sıkıcı ve büyük olasılıkla hataya meyilli bir görev) olarak yeniden yazmak veya uyarıyı devre dışı bırakıp atmaya karar vermek zorunda kalmak gibi talihsiz bir seçimimiz vardır.

Bu durumda, uyarıyı devre dışı bırakmayı tercih ediyoruz. Biz aşağıdaki gibi bir pragma ekleyerek bunu yapabilirsiniz:

```cpp
#pragma warning(disable : 4456)
```

Bir uyarıyı devre dışı bırakırken, yararlı bilgiler sağlayabileceğinde uyarıyı bastırmamak için, devre dışı bırakma efektini yalnızca uyarıyı oluşturan kodla sınırlamak isteyebilirsiniz. Uyarıyı üreten satırdan hemen sonra geri yüklemek için kod ekliyoruz, ya da daha iyisi, bu uyarı bir makroda oluştuğundan, makrolarda çalışan **(makrolarda** çalışmayan)`#pragma` __pragma anahtar sözcük kullanın.

```cpp
#define PARM(var, type, src)__pragma(warning(disable : 4456))  \
type var = (type)src \
__pragma(warning(default : 4456))
```

Sonraki uyarı bazı kod düzeltmeleri gerektirir. Win32 API `GetVersion` (ve) `GetVersionEx`amortismana hazırdır.

```Output
warning C4996: 'GetVersion': was declared deprecated
```

Aşağıdaki kod, sürümün nasıl elde edilir olduğunu gösterir.

```cpp
// check Windows version and set m_bIsWindows9x/m_bIsWindows4x/m_bIsWindows5x flags accordingly.
DWORD dwWindowsVersion = GetVersion();
```

Bunu, Windows 95'te çalışıp çalışmadığımızı ve Windows NT'nin hangi sürümünde çalıştırıp çalıştırılmadığımızı belirlemek için dwWindowsVersion değerini inceleyen çok sayıda kod takip eder. Bu tüm eski olduğundan, kodu kaldırmak ve bu değişkenlere herhangi bir referans ile anlaşma.

Windows [8.1 ve Windows Server 2012 R2'deki işletim sistemi sürümü değişiklikleri,](/windows/win32/w8cookbook/operating-system-version-changes-in-windows-8-1) durumu açıklar.

`CSpyApp` Sınıfta işletim sistemi sürümünü sorgulayan yöntemler vardır: `IsWindows9x`, , `IsWindows4x`ve `IsWindows5x`. İyi bir başlangıç noktası, desteklemek istediğimiz Windows sürümlerinin (Windows 7 ve sonrası) bu eski uygulama tarafından kullanılan teknolojiler söz konusu olduğunda Windows NT 5'e yakın olduğunu varsaymaktır. Bu yöntemlerin kullanımları eski işletim sistemlerinin sınırlamaları ile başa çıkmak için vardı. Bu yüzden diğerleri için TRUE `IsWindows5x` ve FALSE dönmek için bu yöntemleri değiştirdi.

```cpp
BOOL IsWindows9x() {/*return(m_bIsWindows9x);*/ return FALSE;  }
BOOL IsWindows4x() {/*return(m_bIsWindows4x);*/ return FALSE;  }
BOOL IsWindows5x() {/*return(m_bIsWindows5x);*/ return TRUE;  }
```

Bu da iç değişkenlerin doğrudan kullanıldığı birkaç yer bıraktı. Bu değişkenleri kaldırdığımızdan beri, açıkça ilgilenmemiz gereken birkaç hata elde ediyoruz.

```Output
error C2065: 'm_bIsWindows9x': undeclared identifier
```

```cpp
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)
{
  pCmdUI->Enable(m_bIsWindows9x || hToolhelp32 != NULL);
}
```

Bunu bir yöntem çağrısıyla değiştirebilir veya TRUE'yu geçebilir ve Windows 9x için eski özel kılıfı kaldırabiliriz.

```cpp
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)
{
  pCmdUI->Enable(TRUE /*!m_bIsWindows9x || hToolhelp32 != NULL*/);
}
```

Varsayılan düzeydeki son uyarı (3) bit alanıyla ilgilidir.

```Output
treectl.cpp(1656): warning C4463: overflow; assigning 1 to bit-field that can only hold values from -1 to 0
```

Bunu tetikleyen kod aşağıdaki gibidir.

```cpp
m_bStdMouse = TRUE;
```

Bildirge, `m_bStdMouse` bunun bir bit alanı olduğunu gösterir.

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

Bu kod Visual C++'da yerleşik bool türü desteklenmeden önce yazılmıştır. Bu kodda, BOOL **int**için bir **typedef** oldu. Yazı **int** **imzalı** bir türdür ve imzalı bir **int** bit gösterimi bir işaret biti olarak ilk bit kullanmaktır, bu nedenle tür int bir bitfield 0 veya -1 temsil olarak yorumlanabilir, muhtemelen amaçlanan değil.

Bunların neden bit fields olduğunu koda bakarak bilemezsin. Amaç nesnenin boyutunu küçük tutmak için mi, yoksa nesnenin ikili düzeninin kullanıldığı herhangi bir yerde mi? Biz bir bitfield kullanımı için herhangi bir neden görmedim beri sıradan BOOL üyeleri için bu değişti. Bir nesnenin boyutunu küçük tutmak için bit alanlarını kullanmak, çalışmak için garanti değildir. Derleyicinin türünü nasıl ortaya koyduğuna bağlıdır.

Boyunca standart tip **bool** kullanarak yararlı olacağını merak edebilirsiniz. BOOL türü gibi eski kod desenlerinin çoğu daha sonra standart C++'da çözülen sorunları çözmek için icat edilmiştir, bu nedenle BOOL'dan **bool** dahili türüne geçmek, kodunuzu başlangıçta yeni sürümde çalıştırdıktan sonra yapmayı düşündüğünüz bir değişikliğin sadece bir örneğidir.

Varsayılan düzeyde görünen tüm uyarıları ele aldıktan sonra (düzey 3) birkaç ek uyarı yakalamak için seviye 4 olarak değiştirildi. İlk görünen aşağıdaki gibi oldu:

```Output
warning C4100: 'nTab': unreferenced formal parameter
```

Bu uyarıyı oluşturan kod aşağıdaki gibidir.

```cpp
virtual void OnSelectTab(int nTab) {};
```

Bu yeterince zararsız görünüyor, ama biz temiz `/W4` `/WX` bir derleme istedim ve set, biz sadece okunabilirlik uğruna bırakarak, değişken adı dışarı yorumladı.

```cpp
virtual void OnSelectTab(int /*nTab*/) {};
```

Aldığımız diğer uyarılar genel kod temizliği için yararlı oldu. Int veya **imzasız int'ten** WORD'e **int** **(imzasız kısa**için bir yazı türüdür) bir dizi örtük dönüşüm vardır. Bunlar olası bir veri kaybı içerir. Bu gibi durumlarda WORD'e bir döküm ekledik.

Biz bu kod için var başka bir seviye 4 uyarı oldu:

```Output
warning C4211: nonstandard extension used: redefined extern to static
```

Sorun, bir değişken ilk **extern**olarak ilan edildiğinde, daha sonra **statik**olarak bildirildiğinde oluşur. Bu iki depolama sınıfı belirtecinin anlamı birbirini dışlayan dır, ancak bu microsoft uzantısı olarak izin verilir. Kodun diğer derleyicilere taşınabilir olmasını veya (ANSI uyumluluğu) ile `/Za` derlemisini değiştirmek istiyorsanız, bildirimleri eşleşen depolama sınıfı belirteçleri olacak şekilde değiştirirsiniz.

## <a name="step-11-porting-from-mbcs-to-unicode"></a><a name="porting_to_unicode"></a>Adım 11. MBCS'den Unicode'a taşıma

Windows dünyasında, Unicode derken genellikle UTF-16'yı kastettiğimizi unutmayın. Linux gibi diğer işletim sistemleri UTF-8 kullanır, ancak Windows genellikle kullanmaz. MFC'nin MBCS sürümü Visual Studio 2013 ve 2015'te küçümsenmiş olsa da, Visual Studio 2017'de artık amortismana dönüşmemektedir. Visual Studio 2013 veya 2015'i kullanıyorsanız, MBCS kodunu UTF-16 Unicode'a taşıma adımını atmadan önce, başka işler yapmak veya taşımayı uygun bir zamana kadar ertelemek için MBCS'nin amortismana kaldırıldığına dair uyarıları geçici olarak ortadan kaldırmak isteyebiliriz. Geçerli kod MBCS kullanır ve biz MFC ANSI / MBCS sürümünü yüklemek gerekir devam etmek. Oldukça büyük MFC **kitaplığı, C++ yüklemesi ile** varsayılan Visual Studio Desktop geliştirmesinin bir parçası değildir, bu nedenle yükleyicideki isteğe bağlı bileşenlerden seçilmelidir. Bkz. [MFC MBCS DLL Eklentisi.](../mfc/mfc-mbcs-dll-add-on.md) Bunu indirip Visual Studio'yu yeniden başlattıktan sonra, MFC'nin MBCS sürümünü derleyebilir ve bağlantı kurabilirsiniz, ancak Visual Studio 2013 veya 2015 kullanıyorsanız MBCS ile ilgili uyarılardan kurtulmak için, proje özelliklerinin **Önişlemci** bölümünde veya *stdafx.h* başlık dosyanızın veya diğer ortak başlık dosyanızın başında önceden tanımlanmış makrolar listenize NO_WARN_MBCS_MFC_DEPRECATION eklemeniz gerekir.

Şimdi bazı bağlayıcı hataları var.

```Output
fatal error LNK1181: cannot open input file 'mfc42d.lib'
```

LNK1181, bağlayıcı girişine mfc'nin eski statik kitaplık sürümü eklenmiş olduğundan oluşur. MFC'yi dinamik olarak bağlayabildiğimiz için artık bu gerekli değildir, bu nedenle proje özelliklerinin **Bağlantı** bölümündeki **Giriş** özelliğindeki tüm MFC statik kitaplıklarını kaldırmamız gerekir. Bu proje de `/NODEFAULTLIB` seçeneği kullanıyor ve bunun yerine tüm kitaplık bağımlılıklarını listeler.

```
msvcrtd.lib;msvcirtd.lib;kernel32.lib;user32.lib;gdi32.lib;advapi32.lib;Debug\SpyHk55.lib;%(AdditionalDependencies)
```

Şimdi eski Çok bayt karakter kümesini (MBCS) Unicode'a güncelleyelim. Bu, Windows masaüstü platformuna yakından bağlı bir Windows uygulaması olduğundan, windows'un kullandığı UTF-16 Unicode'a bağlantı dalacağız. Platformlar arası kod yazıyorsanız veya bir Windows uygulamasını başka bir platforma taşımayı düşünüyorsanız, diğer işletim sistemlerinde yaygın olarak kullanılan UTF-8'e geçmeyi düşünebilirsiniz.

UTF-16 Unicode'a taşımada, mbcs'ye derleme seçeneğinin hala gerekip gerekmediğine karar vermeliyiz.  MBCS'yi destekleme seçeneğine sahip olmak istiyorsak, Derleme sırasında MBCS \_veya \_UNICODE'un tanımlanıp tanımlanmadığına bağlı **olarak, char** veya **wchar_t**olarak çözülen karakter türü olarak TCHAR makroyu kullanmalıyız. **wchar_t** yerine TCHAR ve çeşitli API'lerin TCHAR sürümlerine ve ilişkili API'lerine geçiş yapmak, \_ \_unicode yerine MBCS makrosu tanımlayarak kodunuzu MBCS sürümüne geri dönebileceğiniz anlamına gelir. TCHAR'a ek olarak, yaygın olarak kullanılan typedef'ler, makrolar ve işlevler gibi çeşitli TCHAR sürümleri de vardır. Örneğin, LPCSTR yerine LPCTSTR ve benzeri. Proje özellikleri iletişim kutusunda, **Yapılandırma Özellikleri**altında, **Genel** bölümde, **Unicode Karakter Kümesini Kullanmak**için **MBCS Karakter Kümesi'ni kullanın** Karakter **Kümesi** özelliğini değiştirin. Bu ayar, derleme sırasında hangi makronun önceden tanımlandığını etkiler. Hem UNICODE makrosu hem \_de UNICODE makrosu vardır. Proje özelliği her ikisini de tutarlı bir şekilde etkiler. Windows üstleleri, MFC gibi Visual C++ üstleleri UNICODE'u kullandığı, \_ancak biri tanımlandığında diğerinin her zaman tanımlandığı UNICODE'u kullanır.

TCHAR kullanarak MBCS'den UTF-16 Unicode'a taşıma için iyi bir [kılavuz](/previous-versions/cc194801(v=msdn.10)) vardır. Bu yolu seçiyoruz. İlk olarak, **Karakter Kümesi** özelliğini **Unicode Karakter Kümesi'ni kullanmak** ve projeyi yeniden oluşturmak için değiştiriyoruz.

Kodbazı yerlerde zaten Sonunda Unicode destekleyen beklentisiyle, TCHAR kullanıyorlardı. Bazıları değildi. Char **için**bir **typedef** olan CHAR örneklerini aradık ve bunların çoğunu TCHAR ile değiştirdik. Ayrıca, biz `sizeof(CHAR)`aradı . Char'dan TCHAR'a her geçiş yaptığımızda, `sizeof(TCHAR)` genellikle bu dizedeki karakter sayısını belirlemek için kullanıldığından değiştirmek zorunda kaldık. Burada yanlış türü kullanarak bir derleyici hatası üretmez, bu nedenle bu durumda biraz dikkat değer.

Bu tür hatalar Unicode'a geçtikten hemen sonra çok yaygındır.

```Output
error C2664: 'int wsprintfW(LPWSTR,LPCWSTR,...)': cannot convert argument 1 from 'CHAR [16]' to 'LPWSTR'
```

Bunu üreten bir kod örneği aşağıda verilmiştir:

```cpp
wsprintf(szTmp, "%d.%2.2d.%4.4d", rmj, rmm, rup);
```

Hatayı \_kaldırmak için T'yi dize etrafında yerleştirdik.

```cpp
wsprintf(szTmp, _T("%d.%2.2d.%4.4d"), rmj, rmm, rup);
```

T makro, MBCS veya UNICODE ayarına bağlı olarak, bir dize edebi derleme **bir char** dize veya wchar_t dize olarak yapma etkisi vardır. **wchar_t** \_ Visual Studio'da \_tüm dizeleri T ile değiştirmek için önce **Hızlı Değiştir** (Klavye: **Ctrl**+**F**) kutusunu veya **Dosyaları Değiştir** kutusunu (Klavye: **Ctrl**+**Shift**+**H)** açın ve **ardından Düzenli İfadeleri Kullan** onay kutusunu seçin. Arama `((\".*?\")|('.+?'))` metni olarak `_T($1)` ve değiştirilen metin olarak girin. Zaten bazı dizeleri \_etrafında T makro varsa, bu yordamı yeniden ekler ve aynı zamanda \_T istemediğiniz durumlarda `#include`bulabilirsiniz, kullandığınızda gibi , bu yüzden **tümünü değiştir**yerine **Sonraki Değiştir'i** kullanmak en iyisidir.

Bu özel işlev, [wsprintf](/windows/win32/api/winuser/nf-winuser-wsprintfw), aslında Windows başlıkları tanımlanır ve bunun için belgeler, olası arabellek taşma nedeniyle kullanılmamasını önerir. `szTmp` Arabellek için boyut verilmez, bu nedenle işlevin arabelleğe yazılması gereken tüm verileri tutup tutayababileceğini denetlemesi için bir yol yoktur. Diğer benzer sorunları çözeceğimiz Güvenli CRT'ye taşıma yla ilgili bir sonraki bölüme bakın. [Biz _stprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)ile değiştirerek sona erdi .

Unicode'a dönüştürmede göreceğiniz bir diğer yaygın hata da butür.

```Output
error C2440: '=': cannot convert from 'char *' to 'TCHAR *'
```

Bunu oluşturan kod aşağıdaki gibidir:

```cpp
pParentNode->m_szText = new char[strTitle.GetLength() + 1];
_tcscpy(pParentNode->m_szText, strTitle);
```

İşlev `_tcscpy` kullanılmış olsa da, bir dize kopyalamak için TCHAR strcpy işlevi, ayrılan arabellek bir **char** arabellek oldu. Bu kolayca TCHAR olarak değiştirilir.

```cpp
pParentNode->m_szText = new TCHAR[strTitle.GetLength() + 1];
_tcscpy(pParentNode->m_szText, strTitle);
```

Benzer şekilde, bir derleyici hatası yla garanti edildiğinde sırasıyla LPSTR (Long Pointer to STRing) ve LPCSTR (Uzun İşaretçi'yi Sabit STRing) ve LPCTSTR (Uzun İşaretçi'den TCHAR STRing'e) ve LPCTSTR (Uzun İşaretçi) olarak değiştirdik. Her durumun ayrı ayrı incelenmesi gerektiği için, küresel arama ve değiştirme kullanarak bu tür değiştirmeler yapmamayı seçtik. Bazı durumlarda, **A** soneki olan Windows yapılarını kullanan belirli Windows iletilerini işlerken olduğu gibi **char** sürümü istenir. Windows API'sinde **A** soneki ASCII veya ANSI (ve MBCS için de geçerlidir) anlamına gelir ve **W** soneki geniş karakterler veya UTF-16 Unicode anlamına gelir. Bu adlandırma deseni Windows üstbilgilerinde kullanılır, ancak yalnızca MBCS sürümünde tanımlanmış bir işlevin Unicode sürümünü eklemek zorunda kaldığımız zaman spy++ kodunda da izledik.

Bazı durumlarda doğru çözen bir sürümü kullanmak için bir tür değiştirmek zorunda kaldık (örneğin WNDCLASSA yerine WNDCLASS).

Birçok durumda biz (yerine) gibi `GetClassName` bir Win32 API genel sürümünü `GetClassNameA`(makro) kullanmak zorunda kaldı. İleti işleyicisi anahtarı deyiminde, bazı iletiler MBCS veya Unicode'a özgüdür, bu gibi durumlarda, genel olarak adlandırılmış işlevleri **A** ve **W** belirli işlevlerle değiştirdiğimiz ve UNICODE tanımlı olup olmadığına bağlı olarak doğru **A** veya **W** adına çözüm veren genel ad için bir makro eklediğimiz için kodu MBCS sürümünü açıkça aramak üzere değiştirmemiz gerekiyordu.  Kodun birçok yerinde, UNICODE'u \_tanımlamak için geçiş yaptığımızda, **A** sürümü istendiğinde bile W sürümü seçilir.

Özel eylemlerin yapılması gereken birkaç yer var. Herhangi bir `WideCharToMultiByte` `MultiByteToWideChar` kullanım veya daha yakından bakmak gerektirebilir. Burada kullanılan bir `WideCharToMultiByte` örnek.

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

Bunu gidermek için, bunun yapılmasının nedeninin bir yazı tipinin adını temsil eden geniş bir karakter dizesini bir `CString`. `strFace`. Bu geniş karakter `CString` `CString` dizeleri için çok bayt dizeleri için biraz `#ifdef` farklı kod gerekli, bu yüzden bu durumda bir ekledi.

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

Tabii ki, `wcscpy` yerine biz `wcscpy_s`gerçekten kullanmalıyız , daha güvenli sürümü. Sonraki bölüm bu adresleri.

Çalışmalarımızı kontrol etmek için, **Çok Bayt Karakter Kümesini Kullanmak** Için Karakter **Kümesini** sıfırlamalı ve kodun MBCS ve Unicode kullanılarak hala derlenmiş olduğundan emin olmalıyız. Söylemeye gerek yok, tam bir test pass tüm bu değişikliklerden sonra yeniden derlenen uygulama üzerinde yürütülmelidir.

Bu Spy++ çözümüyle olan çalışmamızda, ortalama bir C++ geliştiricisinin kodu Unicode'a dönüştürmesi yaklaşık iki iş günü sürdü. Bu, yeniden test süresini içermiş.

## <a name="step-12-porting-to-use-the-secure-crt"></a><a name="porting_to_secure_crt"></a>Adım 12. Güvenli CRT'yi kullanmak için taşıma

Sırada CRT işlevlerinin güvenli sürümlerini **(_s** sonekli sürümler) kullanmak üzere kod taşıma yapılır. Bu durumda, genel strateji işlevi **_s** sürümüyle değiştirmek ve genellikle gerekli ek arabellek boyutu parametrelerini eklemektir. Boyutu bilindiğinden, çoğu durumda bu basittir. Boyutun hemen kullanılamadığı diğer durumlarda, CRT işlevini kullanan işleve ek parametreler eklemek veya hedef arabelleğenin kullanımını incelemek ve uygun boyut sınırlarının ne olduğunu görmek gerekir.

Visual C++ birçok boyut parametresi eklemeden kodu güvenli hale getirmek için bir hile sağlar ve bu da şablonu aşırı yüklerkullanarak olur. Bu aşırı yüklemeler şablonlar olduğundan, c++ olarak derlenirken kullanılabilirler, C. Spyxxhk c projesi olduğu için değil, bu nedenle hile bunun için çalışmaz.  Ancak, Spyxx değildir ve biz hile kullanabilirsiniz. İşin püf noktası, projenin her dosyasında derlenecek bir yerde böyle bir satır eklemektir, örneğin stdafx.h'de:

```cpp
#define _CRT_SECURE_TEMPLATE_OVERLOADS 1
```

Bunu tanımladığınızda, arabellek ham işaretçi yerine bir dizi olduğunda, boyutu dizi türünden çıkarılır ve bunu sağlamanız gerekmeden boyut parametresi olarak kullanılır. Bu, kodu yeniden yazmanın karmaşıklığını azaltmaya yardımcı olur. Yine de işlev adını **_s** sürümüyle değiştirmeniz gerekir, ancak bu genellikle bir arama ve değiştirme işlemi yle yapılabilir.

Bazı işlevlerin dönüş değerleri değişti. Örneğin, `_itoa_s` (ve `_itow_s` makro) `_itot_s`dize yerine`errno_t`bir hata kodu () döndürür. Bu durumda, aramayı ayrı bir satıra `_itoa_s` taşıyıp arabelleğenin tanımlayıcısıyla değiştirmeniz gerekir.

Bazı yaygın durumlarda: `memcpy`için , `memcpy_s`geçiş yaparken , sık sık kopyalanan yapının boyutunu ekledi. Benzer şekilde, çoğu dize ve arabellek için, dizi veya arabellek boyutu kolayca arabellek bildiriminden veya arabellek ilk tahsis edildi nerede bularak belirlenir. Bazı durumlarda, arabellek büyük aslında ne kadar büyük olduğunu belirlemeniz gerekir ve bu bilgi değiştirdiğiniz işlevin kapsamında kullanılamıyorsa, ek bir parametre olarak eklenmelidir ve çağrı kodu bilgileri sağlamak için değiştirilmelidir.

Bu tekniklerle, kodu güvenli CRT işlevlerini kullanmak üzere dönüştürmek yaklaşık yarım gün sürdü. Şablonun aşırı yüklerini kullanmamayı ve boyut parametrelerini el ile eklemeyi seçerseniz, büyük olasılıkla iki veya üç kat daha fazla zaman alır.

## <a name="step-13-zcforscope--is-deprecated"></a><a name="deprecated_forscope"></a>Adım 13. /Zc:forScope- amortismana hazır

Visual C++ 6.0'dan beri derleyici, döngüde bildirilen değişkenlerin kapsamını döngü kapsamına sınırlayan geçerli standarda uygundur. Derleyici seçeneği [/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) ( Proje özelliklerinde**Döngü Kapsamı için Kuvvet Uygunluğu)** bunun bir hata olarak bildirilip bildirilmediğini denetler. Kodumuzu uyumlu olacak şekilde güncellemeli ve döngünün hemen dışına bildirimler eklemeliyiz. Kod değişikliklerini yapmamak için, C++ proje özelliklerinin **Dil** bölümündeki `No (/Zc:forScope-)`bu ayarı ' da ' olarak değiştirebilirsiniz Ancak, Visual C++'ın gelecekteki sürümünde `/Zc:forScope-` kaldırılabileceğini unutmayın, bu nedenle sonunda kodunuzu standarda uyacak şekilde değiştirmek gerekir.

Bu sorunları gidermek nispeten kolaydır, ancak kodunuza bağlı olarak, çok sayıda kodu etkileyebilir. İşte tipik bir sorun.

```cpp
int CPerfTextDataBase::NumStrings(LPCTSTR mszStrings) const
{
  for (int n = 0; mszStrings[0] != 0; n++)
  mszStrings = _tcschr(mszStrings, 0) + 1;
  return(n);
}
```

Yukarıdaki kod hata üretir:

```Output
'n': undeclared identifier
```

Bunun nedeni, derleyicinin artık C++ standardına uygun olmayan koda izin veren bir derleyici seçeneğini amortismana uyması nedeniyle oluşur. Standartta, bir döngü içinde bir değişkenin bildirilmesi kapsamını yalnızca döngüyle sınırlandırdığı ndan, döngü dışında bir döngü sayacı kullanma nın yaygın uygulaması, aşağıdaki gözden geçirilmiş kodda olduğu gibi sayacın bildiriminin de döngü dışına taşınmasını gerektirir:

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

Orijinal Visual C++ 6.0 kodundan en son derleyiciye Spy++'ı taşımak yaklaşık bir hafta boyunca yaklaşık 20 saat kodlama süresi aldı. Visual Studio 6.0'dan Visual Studio 2015'e kadar ürünün sekiz serbest bölümüne doğrudan yükselttik. Bu şimdi büyük ve küçük projelerde tüm yükseltmeleri için önerilen bir yaklaşımdır.

## <a name="see-also"></a>Ayrıca bkz.

[Taşıma ve Yükseltme: Örnekler ve Örnek Olay İncelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Önceki vaka çalışması: COM Spy](../porting/porting-guide-com-spy.md)
