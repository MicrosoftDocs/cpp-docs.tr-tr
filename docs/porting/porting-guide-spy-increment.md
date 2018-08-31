---
title: 'Taşıma Kılavuzu: Spy ++ | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e558f759-3017-48a7-95a9-b5b779d5e51d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 019e63009706fd5d0ab22044642449c5bce3c3a6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222387"
---
# <a name="porting-guide-spy"></a>Taşıma Kılavuzu: Spy++
Bu taşıma örnek olay incelemesi, hangi normal bir taşıma projesinin benzer bir fikir vermek için tasarlanmıştır, karşılaşabileceğiniz sorunları türlerini ve bazı genel ipuçları ve püf noktaları bağlantı noktası oluşturma sorunları ele almak için. Bu proje taşıma deneyimi kod ayrıntılarına bağlı çok bağlı olduğundan taşıma için eksiksiz bir kılavuz olacak şekilde tasarlanmış değil.  
  
## <a name="spy"></a>Spy++  
 
Spy ++ GUI yaygın olarak kullanılan bir tanılama aracı Windows masaüstünde türlerdeki kullanıcı arabirimi öğeleri hakkında bilgi sağlayan Windows Masaüstü için olan. Windows'un tam hiyerarşisini gösterir ve her bir pencere ve denetimi hakkında meta verilerine erişim sağlar. Bu faydalı bir uygulama ile Visual Studio yıllardır sevk edildi. Visual C++ 6.0 ile son derlenen ve Visual Studio 2015 için unity'nin eski bir sürümü bu bulduk. Visual Studio 2017 için deneyimi neredeyse aynı olmalıdır.
  
Özellikle Visual C++ 6.0 itibaren her bir Visual C++ sürümü ile güncelleştirilmemiş eski projeleri için MFC ve Win32 API kullanan bir Windows Masaüstü uygulamaları taşıma için tipik olarak bu durum dikkate.  
  
##  <a name="convert_project_file"></a> 1. adımı. Proje dosyası dönüştürülüyor.  

Proje dosyası, Visual C++ 6.0, iki eski .dsw dosyalarından kolayca daha fazla dikkat gerektiren herhangi bir sorun olmadan dönüştürülür. Spy ++ uygulama bir projedir. Diğer destekleyici bir DLL C dilinde yazılan SpyHk, olur. Daha karmaşık projeler yükseltme olarak kolayca açıklandığı gibi [burada](../porting/visual-cpp-porting-and-upgrading-guide.md).  
  
İki proje yükselttikten sonra Çözümümüzü şöyle Aranan:  
  
![Spy&#43; &#43; çözüm](../porting/media/spyxxsolution.PNG "SpyxxSolution")  
  
C dilinde yazılmış bir DLL ile çok sayıda C++ dosyaları ve başka iki proje sunuyoruz  
  
##  <a name="header_file_problems"></a> 2. adımı. Üstbilgi dosya sorunları  

Yeni dönüştürülmüş proje oluşturma sırasında genellikle bulabilirsiniz gereken ilk unsur projenizin kullandığı üst bilgi dosyaları bulunamadı biridir.  
  
Spy ++'ta bulunamadı dosyaları verstamp.h biriydi. Bir Internet arama aracında bu eski veri teknoloji bir DAO SDK'sından gelen belirledi. Hangi simgelerin, üstbilgi dosyasından bu dosyayı gerçekten gerekirse veya üst bilgi dosyası bildirimi geçersiz kılınan ve yeniden derlenen şekilde bu sembolleri başka bir yerde tanımlanırsa görmek için kullanılan bulmak istedik. Olabilmesinin VER_FILEFLAGSMASK gereklidir, tek bir simge.  
  
```  
1>C:\Program Files (x86)\Windows Kits\8.1\Include\shared\common.ver(212): error RC2104: undefined keyword or key name: VER_FILEFLAGSMASK  
```  
  
Bir sembol kullanılabilir ekleme dosyalarını bulmak için en kolay yolu kullanmaktır **dosyalarda Bul** (**Ctrl**+**Shift**+**F**) belirtin **Visual C++ ekleme dizinleri**. Biz ntverp.h bulundu. Biz verstamp.h yerine ile ntverp.h içerir ve bu hata görünmüyor.  
  
##  <a name="linker_output_settings"></a> 3. adım. Bağlayıcı OutputFile ayarı  

Eski projeler bazen yükselttikten sonra sorunlara neden olabilecek sıra dışı konumlarda yerleştirilen dosyaları gerekir. Bu durumda, biz eklemek zorunda `$(SolutionDir)` için **INCLUDE** var. yerleştirilir bazı başlık dosyalarını Visual Studio bulabileceğinizden emin olmak için proje özelliklerinde yerine proje klasörleri birinde yolu.  
  
MSBuild şeklinde hata verir, **Link.OutputFile** özellik eşleşmiyor **TargetPath** ve **TargetName** MSB8012 veren değerler.  
  
```Output  
warning MSB8012: TargetPath(...\spyxx\spyxxhk\.\..\Debug\SpyxxHk.dll) does not match the Linker's OutputFile property value (...\spyxx\Debug\SpyHk55.dll). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).warning MSB8012: TargetName(SpyxxHk) does not match the Linker's OutputFile property value (SpyHk55). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).  
```  
  
**Link.OutputFile** yapı çıktı (EXE, DLL, örneğin) ve nesnesinden normalde oluşturulan `$(TargetDir)$(TargetName)$(TargetExt)`, yol ve dosya adı uzantısı sağlar. Eski Visual C++ projeleri geçirme Aracı (vcbuild.exe) oluşturduğunuzda Yeni derleme aracını (MSBuild.exe) sık karşılaşılan budur. Visual Studio 2010'da derleme aracı değişikliğinin olduğundan, bu bir pre-2010 project 2010'a geçişi olduğunda sorunu veya sonraki bir sürümünü karşılaşabilirsiniz. Proje Yükseltme Sihirbazı'nı güncelleştirmez temel sorun olduğunu **Link.OutputFile** her zaman değeri olması gerektiğini belirlemek mümkün olmadığından değer bir proje ayarlarına göre. Bu nedenle, genellikle el ile ayarlamanız gerekir. Daha fazla ayrıntı için bkz. Bu [sonrası](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx) Visual C++ blogundaki.  
  
Bu durumda, **Link.OutputFile** dönüştürülmüş projedeki özellik,.\Debug\Spyxx.exe ve yapılandırmasına bağlı olarak Spy ++ projesi için.\Release\Spyxx.exe ayarlandığı. En iyi yol olduğundan bu sabit kodlanmış değerler ile değiştirilecek `$(TargetDir)$(TargetName)$(TargetExt)` için **yapılandırmalarında**. Bu işe yaramazsa, buradan özelleştirme, veya özellikleri değiştirmek **genel** bölümünde bu değerlerin ayarlandığı (özellikleri **çıkış dizinine**, **hedefadı**, ve **hedef uzantısı**. Görüntülemekte olduğunuz özelliği makroları kullanıyorsa, seçebilirsiniz anımsa **Düzenle** yapılan makrosu değişimler ile son dizede gösteren bir iletişim kutusu açmak için aşağı açılan listede. Tüm uygun makroları ve geçerli değerlerini seçerek görüntüleyebilirsiniz **makroları** düğmesi.  
  
##  <a name="updating_winver"></a> 4. adımı. Hedef Windows sürümü güncelleştiriliyor  

MFC'de WINVER sürümü artık desteklenmiyor, bir sonraki hata gösterir. Windows XP için WINVER 0x0501 ' dir.  
  
```Output  
C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxv_w32.h(40): fatal error C1189: #error:  MFC does not support WINVER less than 0x0501.  Please change the definition of WINVER in your project properties or precompiled header.  
```  
  
Onu hedefleyen Visual Studio 2015'te kullanılabilir olsa bile,, uygulamalarınızda desteği geçirebileceğinizden ve kullanıcılarınızın Windows yeni sürümlerini benimsemeye teşvik Windows XP artık Microsoft tarafından desteklenir.  
  
 Hatadan kurtulmak için WINVER güncelleştirerek tanımlamanız **proje özellikleri** şu anda hedeflemek istediğiniz Windows için en düşük sürümünü ayarlama. Çeşitli Windows sürümleri için değerlerinin bir tablosunu bulun [burada](/windows/desktop/WinProg/using-the-windows-headers).  
  
Bu makro tanımları bazıları stdafx.h dosyası içeriyor.  
  
```cpp  
#define WINVER       0x0500  // these defines are set so that we get the  
#define _WIN32_WINNT 0x0500  // maximum set of message/flag definitions,  
#define _WIN32_IE    0x0400  // from both winuser.h and commctrl.h.    
```  
  
Windows 7'ye WINVER ayarlayacağız. Kod (_WIN32_WINNT_WIN7), Windows 7 için makro kullanırsanız, daha sonra değerin kendisi (0x0601'i) yerine okumak daha kolaydır.  
  
```cpp  
#define WINVER _WINNT_WIN32_WIN7 // Minimum targeted Windows version is Windows 7  
```  
  
##  <a name="linker_errors"></a> 5. adımı. Bağlayıcı hataları  

Bu değişikliklerle SpyHk (DLL) projesi oluşturulur, ancak bir bağlayıcı hatası oluşturur.  
  
```  
LINK : warning LNK4216: Exported entry point _DLLEntryPoint@12  
```  
  
Bir DLL giriş noktası verilebilir. Giriş noktası yalnızca diğer arayanlar için dışa aktarma tablosunda olmamalıdır şekilde DLL belleğe ilk yüklendiğinde yükleyicisi tarafından çağrılması amaçlanmıştır. Yalnızca bu yok emin olmak ihtiyacımız **__declspec(dllexport)** yönergesi kendisine bağlı. İki yerde, bildirimi ve tanımı kaldırmak sahibiz spyxxhk.c içinde `DLLEntryPoint`. Hiçbir zaman bu yönerge kullanmak mantıklı bir seçimdi, ancak derleyici ve bağlayıcı önceki sürümlerinde, bir sorun olarak bayrak. Bağlayıcı daha yeni sürümleri bir uyarı verir.  
  
```cpp  
// deleted __declspec(dllexport)  
BOOL WINAPI DLLEntryPoint(HINSTANCE hinstDLL,DWORD fdwReason, LPVOID lpvReserved);    
```  
  
Artık SpyHK.dll, C DLL projesi oluşturur ve hatasız bağlar.  
  
##  <a name="outdated_header_files"></a> 6. adım. Daha eski bir üst bilgi dosyaları  
 
Bu noktada biz çalışma ana yürütülebilir projeye Spyxx başlatın.  
  
Birkaç diğer ekleme kodu dosyaları bulunamadı: ctl3d.h ve penwin.h. Bazen bilgi üstbilgi neleri belirlemeye çalışın Internet'e aramak faydalı olabilir ancak bu yararlı değildir. Biz ctl3d.h Exchange Geliştirme Seti parçası olan ve belirli bir stil denetimleri Windows 95 için destek sağlanır ve penceresinde kalem bilgi işlem için geçersiz bir API penwin.h ilişkili olduğunu öğrenmiştir. Bu durumda, biz yalnızca açıklama `#include` satır ve verstamp.h ile yaptığımız gibi tanımlanmamış sembol ile Dağıt. 3B denetimleri veya kalem bilgi işlem ilgili her şeyi projeden kaldırıldı.  
  
Aşamalı olarak ortadan birçok derleme hataları içeren bir proje göz önünde bulundurulduğunda, güncel olmayan bir API'nin tüm kullanımları hemen kaldırdığınızda bulmak için gerçekçi değildir `#include` yönergesi. Biz bunu hemen, ancak bunun yerine bir noktada algılamadık daha sonra gelen WM_DLGBORDER tanımlanmamış bir hata oluştu. Aslında yalnızca bir tane olan birçok tanımlanmamış ctl3d.h gelen semboller. Biz güncel olmayan bir API'ye ilişkili saptadıktan sonra tüm başvuruları, kodu kaldırdık.  
  
##  <a name="updating_iostreams_code"></a> 7. adımı. Eski iostreams kodunu güncelleştirme  
 
İostreams kullanan eski C++ kodu ile bir sonraki hata yaygındır.  
  
mstream.h(40): önemli hata C1083: açık dosya içeremez: 'iostream.h': Böyle bir dosya veya dizin  
  
Eski iostreams kitaplığı kaldırılmış ve yerine sorunudur. Eski iostreams yeni standartları ile değiştirilecek sahibiz.  
  
```cpp  
#include <iostream.h>  
#include <strstrea.h>  
#include <iomanip.h>    
```  
  
Güncelleştirilmiş bunlar içerir:  
  
```cpp  
#include <iostream>  
#include <sstream>  
#include <iomanip>    
```  
  
Bu değişiklik, biz sorunlarınız `ostrstream`, artık kullanılır. Uygun yerini ostringstream alır. Eklemeyi deneyin bir **typedef** için `ostrstream` kodunda değişiklik çok büyük bir başlangıç olarak en az önlemek için.  
  
```cpp  
typedef std::basic_ostringstream<TCHAR> ostrstream;    
```  
  
Proje MBCS (çok baytlı karakter kümesi), bunu kullanarak şu anda oluşturulan **char** uygun karakter veri türü. Ancak, daha kolay bir güncelleştirme UTF-16 Unicode kod izin vermek için bu güncelleştiriyoruz `TCHAR`, çözümler için **char** veya **wchar_t** bağlı olarak **karakterkümesi** MBCS ya da Unicode proje ayarlarını özelliğinde ayarlanır.  
  
Bazı kod parçalarını güncelleştirilmesi gerekir.  Biz taban sınıfı yerine `ios` ile `ios_base`, biz ostream değiştirildi basic_ostream tarafından olan\<T >. Biz iki ek tür tanımları ekleyin ve bu bölümde derler.  
  
```cpp  
typedef std::basic_ostream<TCHAR> ostream;  
typedef ios_base ios;    
```  
  
Bu tür tanımları yalnızca geçici bir çözüm kullanmaktır. Daha kalıcı bir çözüm için biz yeniden adlandırılmış veya güncel olmayan API'sine yapılan her başvuru güncelleştirebilir.  
  
Sonraki hata aşağıda verilmiştir.  
  
```Output  
error C2039: 'freeze': is not a member of 'std::basic_stringbuf<char,std::char_traits<char>,std::allocator<char>>'  
```  
  
Sonraki sorun olan `basic_stringbuf` sahip olmayan bir `freeze` yöntemi. `freeze` Yöntemi eski bir bellek sızıntısı önlemek için kullanılan `ostream`. Kullandığımız yeni göre ihtiyacımız `ostringstream`. Çağrı silmemiz `freeze`.  
  
```cpp  
//rdbuf()->freeze(0);  
```  
  
Sonraki iki bitişik satırlarında hata. İlk kullanma hakkında şeklinde hata verir `ends`, eski olan `iostream` kitaplığın g/ç bir dizeye null sonlandırıcıyı ekleyen bir işleyici. Bu hataların ikinci bilgiler veren çıktısını `str` yöntemi bir const olmayan işaretçisine atanamaz.  
  
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
  
Yeni akış kitaplığı kullanarak `ends` böylece satır kaldırılabilir null ile sonlandırılmış dize her zaman olduğu gerekli değildir. İkinci sorun için, artık sorunudur `str()` ; dize karakter dizisine bir işaretçi döndürmüyor döndürür `std::string` türü. İkinci çözüm türüne değiştirmektir `LPCSTR` ve `c_str()` işaretçi istemek için yöntemi.  
  
```cpp  
//*this << ends;  
LPCTSTR psz = str().c_str();    
```  
  
Bize biraz puzzled bir hata oluştu Bu kodu.  
  
```cpp  
MOUT << _T(" chUser:'") << chUser  
<< _T("' (") << (INT)(UCHAR)chUser << _T(')');    
```  
  
MOUT çözümler için makro \*türünde bir nesne olan g_pmout `mstream`. `mstream` Standart çıkış dizesi sınıfından türetilmiş sınıf `std::basic_ostream<TCHAR>.` ancak biz, aşırı yükleme çözümlemesi için Unicode dönüştürme için hazırlanırken yerleştirecek _T dize sabit değeri, geçici bir çözüm ile **işleci <<** şu hata iletisiyle başarısız olur:  
  
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
  
Bu nedenle kullanabileceğiniz birçok **işleci <<** tanımları bu tür bir hatayı göz korkutucu olabilir. Daha yakından baktığımızda kullanılabilir aşırı çoğunu ilgisiz ve daha yakından adresindeki görünümlü görebiliriz `mstream` sınıf tanımının çağrıldığında bu durumda düşünüyoruz aşağıdaki işlevi belirledik.  
  
```cpp  
mstream& operator<<(LPTSTR psz)  
{  
  return (mstream&)ostrstream::operator<<(psz);  
}    
```  
  
Dize sabit değeri türüne sahip olduğundan değil adlı sebebi `const wchar_t[10]` , uzun bir hata iletisinin son satırından görebileceğiniz gibi bu nedenle sabit olmayan işaretçisine dönüştürme değil otomatik. Parametre türü daha uygun olacak şekilde ancak bu işleç giriş parametresi değiştirmemelisiniz `LPCTSTR` (`const char*` MBCS derlenirken ve `const wchar_t*` Unicode) değil `LPTSTR` (`char*` MBCS ve derlenirken`wchar_t*` Unicode olarak). Bu değişikliği yapmak bu hatayı düzeltir.  
  
Bu tür bir dönüştürme, eski ve daha az katı derleyici altında izin verildi, ancak daha yeni uyum değişiklik daha doğru kod gerektirir.  
  
##  <a name="stricter_conversions"></a> 8. adım. Derleyicinin daha katı dönüştürmeler  
 
Aşağıdaki gibi birçok hata da aldığımız:  
  
```  
error C2440: 'static_cast': cannot convert from 'UINT (__thiscall CHotLinkCtrl::* )(CPoint)' to 'LRESULT (__thiscall CWnd::* )(CPoint)'  
```  
  
Hata, yalnızca bir makrosu ileti eşlemede oluşur:  
  
```cpp  
BEGIN_MESSAGE_MAP(CFindToolIcon, CWnd)  
// other messages omitted...  
ON_WM_NCHITTEST() // Error occurs on this line.  
END_MESSAGE_MAP()  
```  
  
Bu makro tanımına gitme, işlev başvurduğu görüyoruz `OnNcHitTest`.  
  
```cpp  
#define ON_WM_NCHITTEST() \  
{ WM_NCHITTEST, 0, 0, 0, AfxSig_l_p, \  
(AFX_PMSG)(AFX_PMSGW) \  
(static_cast< LRESULT (AFX_MSG_CALL CWnd::*)(CPoint) > (&ThisClass :: OnNcHitTest)) },  
```  
  
Üye işlevi türleri için işaretçi uyuşmazlık ile yapmak sorun vardır. Sorun değil dönüştürme işlemini `CHotLinkCtrl` için bir sınıf türü olarak `CWnd` , geçerli bir temel ile türetilmiş dönüştürme olduğundan sınıf türü olarak. Dönüş türü bir sorundur: UINT vs. LRESULT. UINT bu türe dönüştürme değil, bir 64-bit işaretçi ya da hedef ikili türüne bağlı olarak bir 32 bit işaretçi olan LONG_PTR LRESULT çözümler. Bu çok sayıda ileti eşlemesi yöntemlerin dönüş türü UINT Visual Studio 2005 LRESULT için 64 bit uyumlulukla değişiklikleri bir parçası olarak değiştiğinden, 2005'ten önce yazılmış kod yükseltirken nadir değildir. Dönüş türü biz LRESULT için tek tek aşağıdaki kodda UINT değiştirin:  
  
```cpp  
afx_msg UINT OnNcHitTest(CPoint point);  
```  
  
Değişiklikten sonra aşağıdaki kodu sunuyoruz:  
  
```cpp  
afx_msg LRESULT OnNcHitTest(CPoint point);  
```  
  
Bu işlev CWnd'den türetilen tüm farklı sınıflardaki yaklaşık on oluşumlarını olduğundan, kullanmanız yararlı **Tanıma Git** (klavye: **F12**) ve **bildiriminegidin** (Klavye: **Ctrl**+**F12**) imleç olduğunda bu bulun ve gitmek için düzenleyicide bir işlevde gelen onlara **sembol Bul'u** araç penceresi. **Tanımı Git** genellikle daha iki yararlıdır. **Bildirim Git** tanımlama dışında Bul bildirimleri sınıf bildiriminin, arkadaş sınıf bildirimleri gibi veya ileri başvuru.  
  
##  <a name="mfc_changes"></a> 9. adım. MFC değişiklikleri  
 
Sonraki hataya değiştirilen bildirim türüne de ilgilidir ve ayrıca bir makroda oluşur.  
  
```Output  
error C2440: 'static_cast': cannot convert from 'void (__thiscall CFindWindowDlg::* )(BOOL,HTASK)' to 'void (__thiscall CWnd::* )(BOOL,DWORD)'  
```  
  
İkinci parametresi olan sorunu `CWnd::OnActivateApp` HTASK DWORD için değiştirildi. Bu değişiklik, Visual Studio, Visual Studio .NET 2002 sürümünde oluştu.  
  
```cpp  
afx_msg void OnActivateApp(BOOL bActive, HTASK hTask);  
```  
  
Türetilen sınıfların OnActivateApp bildirimlerinde buna göre şu şekilde güncelleştirmek sunuyoruz:  
  
```cpp  
afx_msg void OnActivateApp(BOOL bActive, DWORD dwThreadId);  
```  
  
Bu noktada, projeyi derlemek yükümlü. Ancak, çalışmak için bazı uyarılar oluştu ve MBCS Unicode'a dönüştürme veya güvenlik güvenli CRT işlevleri kullanarak geliştirme gibi yükseltme, isteğe bağlı bölümden oluşur.  
  
##  <a name="compiler_warnings"></a> 10. adımı. Derleyici uyarılarını adresleme  

Uyarıların tam bir listesini almak için yapmanız bir **Rebuild All** uyarı raporları yalnızca geçerli aldığından çözüm yerine normal bir derleme, yalnızca emin olmak için her şey daha önce derlenmiş, derlenecek derleme. Başka bir sorunuz uyarı düzeyine kabul edin veya daha yüksek bir uyarı düzeyi kullanmayı ' dir.  Kod, özellikle de eski kod taşırken daha yüksek bir uyarı düzeyi kullanarak uygun olabilir.  Varsayılan uyarı düzeyini ile başlatın ve ardından tüm uyarıları almak için uyarı düzeyini artırmak isteyebilirsiniz. Kullanırsanız `/Wall`, bazı uyarılar sistemde üst bilgi dosyaları almak için çoğu kişi kullanın `/W4` sistem üstbilgileri için uyarıları almadan kendi kodlarına en uyarıları almak için. Uyarıları hata olarak görünmesini istiyorsanız ekleyin `/WX` seçeneği. Bu ayarlar **C/C++** bölümünü **proje özellikleri** iletişim kutusu.  
  
Metotlarından birini `CSpyApp` sınıfı artık desteklenmeyen bir işlev hakkında bir uyarı üretir.  
  
```cpp  
void SetDialogBkColor() {CWinApp::SetDialogBkColor(::GetSysColor(COLOR_BTNFACE));}  
```  
  
Uyarı aşağıdaki gibidir.  
  
```Output  
warning C4996: 'CWinApp::SetDialogBkColor': CWinApp::SetDialogBkColor is no longer supported. Instead, handle WM_CTLCOLORDLG in your dialog  
```  
  
İletinin WM_CTLCOLORDLG zaten işlenmiş Spy ++ kodda, tüm başvurularını silmek için gerekli tek değişiklik şekilde `SetDialogBkColor`, artık gereken.  
  
Sonraki uyarı değişken adı olarak ekleyerek düzeltmek kolaydır. Aşağıdaki uyarı aldık:  
  
```Output  
warning C4456: declaration of 'lpszBuffer' hides previous local declaration  
```  
  
Oluşturan bu kod, bir makro içerir.  
  
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
  
Bu kod olduğu gibi makrolar ağır olarak kullanan kod korumak daha zor hale eğilimindedir. Bu durumda, makrolar, değişken bildirimleri içerir. ' % S'makrosu parametre şu şekilde tanımlanır:  
  
```cpp  
#define PARM(var, type, src)type var = (type)src  
```  
  
Bu nedenle `lpszBuffer` değişkeni iki kez aynı işlevde bildirilen. Kod olan kullanmıyorsa, makroları (yalnızca ikinci tür bildirimi Kaldır) olduğu gibi bu sorunu gidermek için bu straightfoward değil. Olduğu gibi sıradan kod (sıkıcı ve büyük olasılıkla hataya görevdir) olarak makro kodu yeniden yazın veya uyarıyı devre dışı bırakmak karar vermek zorunda kalmadan talihsiz seçeneğine sahibiz.  
  
Bu durumda, biz uyarı devre dışı bırakmak için iyileştirilmiş. Şu şekilde bir pragma ekleyerek yapabiliriz:  
  
```cpp  
#pragma warning(disable : 4456)  
```  
  
Uyarı devre dışı bırakma, devre dışı bırakma kısıtlamak isteyebilirsiniz yalnızca kodum yararlı bilgiler sağlayabilir, uyarı gizleme önlemek için uyarı üreten, geçerlilik kazanır. Biz ürettiği satırından sonra uyarıyı geri yüklemek için kod eklemeye veya daha da iyisi, bu uyarı bir makroda oluşur. bu yana kullanın **__pragma** makrolarındaki çalışır anahtar sözcüğü (`#pragma` makrolarındaki çalışmaz).  
  
```cpp  
#define PARM(var, type, src)__pragma(warning(disable : 4456))  \  
type var = (type)src \  
__pragma(warning(default : 4456))    
```  
  
Sonraki uyarı bazı kod sürümlerini gerektirir. Win32 API `GetVersion` (ve `GetVersionEx`) kullanım dışı bırakılmıştır.  
  
```Output  
warning C4996: 'GetVersion': was declared deprecated  
```  
  
Aşağıdaki kod, sürüm nasıl aldıklarına gösterir.  
  
```cpp  
// check Windows version and set m_bIsWindows9x/m_bIsWindows4x/m_bIsWindows5x flags accordingly.  
DWORD dwWindowsVersion = GetVersion();    
```  
  
Bu, dwWindowsVersion değer olup olmadığını biz Windows 95'te çalıştırıyorsanız belirlemek için inceler kod ve hangi sürümü Windows NT tarafından izlenir. Tüm eski olduğundan, biz kodu kaldırın ve değişkenlere yapılan tüm başvuruları uğraşmanız gerekir.  
  
Makaleyi [Windows 8.1 ve Windows Server 2012 R2 işletim sistemi sürüm değişikliklerini](https://msdn.microsoft.com/library/windows/desktop/dn302074.aspx) durumu açıklar.  
  
Yöntemleri vardır `CSpyApp` işletim sistemi sürümü sorgu sınıfı: `IsWindows9x`, `IsWindows4x`, ve `IsWindows5x`. İyi bir başlangıç noktası şu ana kadar bu eski bir uygulama tarafından kullanılan teknolojilerden olarak Windows NT 5 endişe (Windows 7 ve üzeri) desteklemek istediğiniz Windows sürümlerini kapatmak için tüm edileceğidir. Bu yöntemlerin kullandığı eski işletim sistemlerini kısıtlamalarla dağıtılacak yoktu. TRUE döndürmek için bu yöntemleri değiştirdik. böylece `IsWindows5x` ve diğerleri için FALSE.  
  
```cpp  
BOOL IsWindows9x() {/*return(m_bIsWindows9x);*/ return FALSE;  }  
BOOL IsWindows4x() {/*return(m_bIsWindows4x);*/ return FALSE;  }  
BOOL IsWindows5x() {/*return(m_bIsWindows5x);*/ return TRUE;  }    
```  
  
Yalnızca iç değişkenler doğrudan kullanıldığı birkaç yerde sol. Bu değişkenler kaldırdık olduğundan, biz açıkça uğraşmak zorunda birkaç hatalar alınamıyor.  
  
```Output  
error C2065: 'm_bIsWindows9x': undeclared identifier  
```  
  
```cpp  
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)  
{  
  pCmdUI->Enable(m_bIsWindows9x || hToolhelp32 != NULL);  
}    
```  
  
Biz bunu bir yöntem çağrısı veya yalnızca geçişi ile doğru değiştirin ve eski özel durum kaldırmak için Windows 9 x.  
  
```cpp  
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)  
{  
  pCmdUI->Enable(TRUE /*!m_bIsWindows9x || hToolhelp32 != NULL*/);  
}    
```  
  
Son uyarı varsayılan düzeyde (3) bir bit alanı ile ilgilidir.  
  
```Output  
treectl.cpp(1656): warning C4463: overflow; assigning 1 to bit-field that can only hold values from -1 to 0  
```  
  
Bu tetikleyen kod aşağıdaki gibidir.  
  
```cpp  
m_bStdMouse = TRUE;  
```  
  
Bildirimi `m_bStdMouse` bir bit alanı olduğunu gösterir.  
  
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
  
Bu kod, Visual c++'ta yerleşik bool türü destekleniyordu önce yazılmıştır. Bu kodda, BOOL olduğu bir **typedef** için **int**. Türü **int** olduğu bir **imzalı** türü ve bit gösterimi bir **signed int** ilk bit bit alanından mantıksal karşılaştırmaya int türü olarak yorumlanabilecek bir imza biti kullanmak için 0 veya -1 temsil eden, büyük olasılıkla ne üzere tasarlanmıştır.  
  
Koda baktığınızda bildiğiniz mıydı bit alanları bunlar neden. Nesnesinin ikili düzenini kullanıldığı her yerde olduğundan mı nesnenin boyutunu küçük tutmaya amaç mıydı? Bu sıradan BOOL üyelerine değiştirdik biz bir bit alanı kullanımı için herhangi bir nedenle görmediniz olduğundan. Bir nesnenin boyutunu küçük tutmaya bit alanları kullanarak çalışacak şekilde garanti yoktur. Bu, derleyicinin türünün nasıl yerleştirir bağlıdır.  
  
Merak ediyor standart türü kullanıyorsanız **bool** boyunca yardımcı olacaktır. BOOL türü gibi eski kod desenleri birçoğu, standart c++ BOOL değerine gelen şekilde değiştirilmesi, daha sonra çözülen sorunları çözmek için invented **bool** yerleşik türü yalnızca bir örneği böyle bir değişiklik yaptığınızda, sonra göz önünde bulundurun Başlangıçta yeni sürümde çalışan kodunuzu alın.  
  
Biz varsayılan düzeyinde (Düzey 3) görünen tüm uyarıları ile ele sonra birkaç ek uyarılar çekmek için 4 düzeyine değiştirdik. Aşağıdaki gibi görünen ilk şöyleydi:  
  
```Output  
warning C4100: 'nTab': unreferenced formal parameter  
```  
  
Bu uyarı üretilen kod şu şekilde oluştu.  
  
```cpp  
virtual void OnSelectTab(int nTab) {};  
```  
  
Bu yeterince zararsız gibi görünüyor, ancak temiz bir derleme ile istedik beri `/W4` ve `/WX` ayarlayın, biz yalnızca out değişkeni adı, okunabilirlik açısından çıkmadan yorum yaptı.  
  
```cpp  
virtual void OnSelectTab(int /*nTab*/) {};  
```  
  
Aldığımız diğer uyarılar genel kod Temizleme için yararlıdır. Örtük dönüştürmelerine sayıda **int** veya **işaretsiz int** sözcüğe (için bir typedef olduğu **işaretsiz**). Bu, veri kaybını içerir. Bir yayın WORD'e bu gibi durumlarda ekledik.  
  
Bu kod için yapılandırdığımıza başka bir düzey 4 uyarısı şöyleydi:  
  
```Output  
warning C4211: nonstandard extension used: redefined extern to static  
```  
  
Bir değişken ilk bildirildiğinde sorun oluşmadan **extern**, daha sonra bildirilen **statik**. Bu iki depolama sınıfı tanımlayıcıları anlamını birbirini dışlayan olduğu halde bir Microsoft uzantısı olarak izin verilir. Diğer derleyicileri için taşınabilir olması için kodu istiyordu ya da onunla derlemek isteseydiniz `/Za` (ANSI uyumluluğu) bildirimleri depolama sınıfı tanımlayıcıları eşleşen değiştirmeniz.  
  
##  <a name="porting_to_unicode"></a> 11. adım. Unicode MBCS taşıma

Unicode dediğimiz Windows dünyada biz genellikle UTF-16 anlama olduğunu unutmayın. UTF-8 Linux gibi diğer işletim sistemleri kullanın, ancak Windows genellikle desteklemez. MFC MBCS sürümü, 2015 ve Visual Studio 2013'ün de kullanım dışı bırakıldı, ancak artık Visual Studio 2017'de kullanım dışıdır. Visual Studio 2013 veya 2015'te, aslında UTF-16 Unicode MBCS koda bağlantı noktasına adım almadan önce kullanıyorsanız, biz geçici olarak MBCS kullanım dışı uyarılarını ortadan kaldırmak için diğer iş yapmak veya uygun bir zamana kadar taşıma ertelemek için isteyebilirsiniz. Geçerli kod MBCS kullanır ve ANSI/MBCS MFC sürümünü yüklemek ihtiyacımız olan devam etmek için. Daha kapsamlı MFC Kitaplığı Visual Studio varsayılan bir parçası değil **C++ ile masaüstü geliştirme** Yükleyicisi'nde isteğe bağlı bileşenler'den seçilmelidir şekilde yükleme. Bkz: [MFC MBCS DLL eklentisi](../mfc/mfc-mbcs-dll-add-on.md). Önceden tanımlanmış sonra bunu indirmek ve Visual Studio'yu yeniden başlatın, derleyin ve MFC, ancak Visual Studio 2013 veya 2015 kullanıyorsanız, uyarıların MBCS hakkında kurtulabileceğinizi MBCS sürümü ile bağlantı, NO_WARN_MBCS_MFC_DEPRECATION listenize de eklemeniz gerekir Makrolar **önişlemci** Proje Özellikleri'nin veya stdafx.h üst bilgisi dosyanıza veya diğer ortak bir üstbilgi dosyasında başına bölüm.  
  
Artık bazı bağlayıcı hatalar var.  
  
```Output  
fatal error LNK1181: cannot open input file 'mfc42d.lib'  
```  
  
Bir mfc eski statik kitaplık sürümünü giriş bağlayıcı üzerinde dahil olduğundan LNK1181 gerçekleşir. Artık size dinamik olarak MFC'ye bu yana biz yalnızca tüm MFC statik kitaplıklarından kaldırmanız gerekir böylece bunun gerekli olmadığını **giriş** özelliğinde **bağlayıcı** Proje Özellikleri bölümünde. Bu proje de kullanarak `/NODEFAULTLIB` seçeneğini ve bunun yerine, tüm kitaplık bağımlılıkları listeler.  
  
```  
msvcrtd.lib;msvcirtd.lib;kernel32.lib;user32.lib;gdi32.lib;advapi32.lib;Debug\SpyHk55.lib;%(AdditionalDependencies)  
```  
  
Artık bize gerçekten eski çok baytlı karakter kümesi (MBCS) kodu için Unicode güncelleştirin. Bu içkin şekilde Windows Masaüstü platform için bağlı bir Windows uygulaması olduğundan biz bunu kullanan Windows UTF-16 Unicode bağlantı. Platformlar arası kod yazma veya başka bir platform için bir Windows uygulaması bağlantı noktası oluşturma, yaygın olarak kullanılan diğer işletim sistemlerinde UTF-8, taşıma düşünmek isteyebilirsiniz.  
  
UTF-16 Unicode taşıma, biz biz yine de MBCS'den veya derleme seçeneğini istediğinizi karar vermeniz gerekir.  MBCS Desteği seçeneğine sahip olmasını istiyoruz, TCHAR makrosu ya da giderir karakter türü olarak kullanmamız gereken **char** veya **wchar_t**_MBCS veya _UNICODE sırasında tanımlı olup olmadığı bağlı olarak derleme. TCHAR ve TCHAR yerine çeşitli API sürümlerini geçiş **wchar_t** ve onun ilişkili API'ler, geri kodunuzun bir MBCS sürümünü _MBCS makrosu _UNICODE yerine tanımlayarak edinebileceğiniz anlamına gelir. TCHAR ek olarak TCHAR sürümlerini yaygın olarak kullanılan tür tanımları, makrolar ve işlevler gibi çeşitli var. Örneğin, LPCTSTR LPCSTR vb. yerine. Proje Özellikleri iletişim kutusunda, altında **yapılandırma özellikleri**, **genel** bölümünde **karakter kümesi** özelliğinden **MBCS kullanın Karakter kümesi** için **Unicode karakter kümesini Kullandırır**. Bu ayar, hangi makrosu, derleme sırasında önceden etkiler. Bir UNICODE makrosu hem _UNICODE makrosu yoktur. Proje özelliği hem de sürekli olarak etkiler. _UNICODE MFC gibi Visual C++ üstbilgi kullanabilirsiniz, ancak bir tanımlandığında UNICODE Windows üstbilgileri kullanmak, diğeri her zaman tanımlanır.  
  
İyi bir [Kılavuzu](https://msdn.microsoft.com/library/cc194801.aspx) UTF-16 Unicode MBCS taşıma için TCHAR kullanarak mevcut. Biz bu yolu seçin. İlk olarak, biz değiştirme **karakter kümesi** özelliğini **kullanım Unicode karakter kümesi** ve projeyi yeniden derleyin.  
  
Bazı yerlerde kodu zaten TCHAR, görünüşe göre sonuçta Unicode destekleme kapatıldığını içinde kullanıyordu. Bazı değildi. Biz Aranan örnekleri olan char bir **typedef** için **char**ve bunların çoğu TCHAR ile değiştirilir. Ayrıca, incelemiştik `sizeof(CHAR)`. TCHAR için CHAR değiştirdik olduğunda, genellikle değiştirmek vardı `sizeof(TCHAR)` olduğundan, bu genellikle bir dizedeki karakter sayısını belirlemek için kullanıldı. Bu durumda dikkat biraz ödeme değer, bu nedenle burada yanlış türde kullanarak bir derleyici hatası üretmez.  
  
Bu tür için Unicode değiştirdikten sonra çok yaygındır.  
  
```Output  
error C2664: 'int wsprintfW(LPWSTR,LPCWSTR,...)': cannot convert argument 1 from 'CHAR [16]' to 'LPWSTR'  
```  
  
Bu üreten koduna ilişkin bir örnek aşağıda verilmiştir:  
  
```cpp  
wsprintf(szTmp, "%d.%2.2d.%4.4d", rmj, rmm, rup);  
```  
  
Biz _T dize geçici hata kaldırmak için değişmez değer yerleştirin.  
  
```cpp  
wsprintf(szTmp, _T("%d.%2.2d.%4.4d"), rmj, rmm, rup);  
```  
  
_T makro bir dize sabit değeri derleme olarak yapma etkisi bir **char** dize veya bir **wchar_t** UNICODE ve MBCS ayara bağlı olarak bir dize. Visual Studio'da _T tüm dizeleri değiştirmek için önce açın **hızlı Değiştir** (klavye: **Ctrl**+**F**) kutusunu veya **dosyalarda Değiştir**  (Klavye: **Ctrl**+**Shift**+**H**), ardından **normal kullanım İfadeleri** onay kutusu. Girin `((\".*?\")|('.+?'))` arama metni olarak ve `_T($1)` yerine konacak metin olarak. Zaten sahip olduğunuz bazı dizeler _T makrosu, bu yordamı, yeniden ekleyeceksiniz ve kullandığınızda gibi _T, istediğiniz durumlarda da bulabilirsiniz `#include`, kullanmak en iyisidir **Değiştir** yerine  **Tümünü Değiştir**.  
  
 Bu belirli işlev [wsprintf](/windows/desktop/api/winuser/nf-winuser-wsprintfa), bu, olası arabellek taşması nedeniyle kullanılmaması önerir için gerçekten Windows üstbilgiler ve belgeleri tanımlanır. Boyut için verilen `szTmp` arabellek vardır, bu nedenle arabellek için yazılmış veri tutabilen denetlenecek işlevine yönelik bir yolu yoktur. Güvenliğini size benzer diğer sorunları gidermek CRT'ye, taşıma hakkında sonraki bölüme bakın. İle değiştirerek sona [_stprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md).  
  
Başka bir yaygın hata Unicode'a dönüştürürken göreceğiniz budur.  
  
```Output  
error C2440: '=': cannot convert from 'char *' to 'TCHAR *'  
```  
  
Ürettiği kod aşağıdaki gibidir:  
  
```cpp  
pParentNode->m_szText = new char[strTitle.GetLength() + 1];  
_tcscpy(pParentNode->m_szText, strTitle);  
```  
  
Olsa da `_tcscpy` işlevi kullanıldı, bir dizeyi kopyalama için TCHAR strcpy işlevi olduğu, ayrılan bir arabellek bir **char** arabellek. Bu, kolayca TCHAR için değiştirilir.  
  
```cpp  
pParentNode->m_szText = new TCHAR[strTitle.GetLength() + 1];  
_tcscpy(pParentNode->m_szText, strTitle);    
```  
  
Benzer şekilde, LPSTR (uzun dize işaretçisi) ve LPCSTR (uzun sabit dize işaretçisi) LPTSTR (uzun TCHAR dize işaretçisi) ve LPCTSTR (uzun sabit TCHAR dize işaretçisi) sırasıyla bir derleyici hatası garanti edildiği zaman değiştirdik. Her durumda ayrı ayrı incelenmesi çünkü bu tür değişiklik genel arama ve değiştirme, kullanarak yapmamak seçtik. Bazı durumlarda, **char** sürümü istiyordu, ne zaman belirli Windows sahip Windows yapıları kullandığınız iletilerini işleme gibi **A** soneki. Windows API, sonek **A** ASCII veya ANSI anlamına gelir (ve MBCS için de geçerlidir) ve sonek **W** geniş karakterler ya da UTF-16 Unicode anlamına gelir. Bu adlandırma desenine Windows üstbilgileri kullanılır ancak biz yalnızca bir MBCS sürümde zaten tanımlanmış olan bir işlevin bir Unicode sürümü gerekiyordu, ayrıca, Spy ++ kodda izlenen.  
  
Doğru gideren bir sürümünü kullanmak için bir tür değiştirilecek vardı bazı durumlarda (örneğin WNDCLASSA yerine WNDCLASS).  
  
Çoğu durumda biz bir Win32 API gibi genel sürümünü (makro) kullanmanız gerekiyordu `GetClassName` (yerine `GetClassNameA`). İleti işleyici switch deyimi içinde bazı iletilerin bu durumda MBCS veya Unicode özel, biz genel olarak adlandırılan işlevlerin ile değiştirilmiş olduğundan MBCS sürüm açıkça çağırmak için kodu değiştirmenizi vardı **A** ve **W** belirli işlevleri ve çözümlenen doğru genel adı bir makro eklenen **A** veya **W** UNICODE tanımlanan şirket adı.  _UNICODE, tanımlama moduna, seçilen bile artık kod pek çok bölümünün W sürümüdür **A** sürümüdür ne istiyordu.  
  
Burada gerçekleştirilecek özel eylemler b birkaç yerde mevcuttur. Kullanımı `WideCharToMultiByte` veya `MultiByteToWideChar` daha yakından gerektirebilir. İşte bir örnek burada `WideCharToMultiByte` kullanılıyordu.  
  
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
  
Bunu ele almak için Biz bu silme işleminin nedeni dahili arabelleğe yazı tipinin adını temsil eden bir geniş karakter dizesini kopyalayın olduğunu anlamak olan bir `CString`, `strFace`. Bu biraz farklı kod için çok baytlı gerekli `CString` olduğu geniş karakter dizeleri `CString` eklediğimiz için dizeleri bir `#ifdef` bu durumda.  
  
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
  
Elbette, yerine, `wcscpy` gerçekten kullanmamız gereken `wcscpy_s`, daha güvenli bir sürümü. Sonraki bölümde bu giderir.  
  
Yaptığımız çalışmaların üzerinde bir denetimi biz sıfırlamalısınız **karakter kümesi** için **kullanmak çok baytlı karakter kümesi** ve kullanarak MBCS ve Unicode kod hala derlendiğinden emin olun. Deyin needless için bir tam test geçişi bu değişikliklerden sonra znovu uygulama yürütülmelidir.  
  
Bu Spy ++ çözümü sayesinde işimizi kod, Unicode'a dönüştürmenin ortalama bir C++ geliştiricileri için yaklaşık iki çalışma günlerini sürdü. Bu, retesting zaman içermiyordu.  
  
##  <a name="porting_to_secure_crt"></a> 12. adımı. Güvenli CRT kullanılacak bağlantı noktası oluşturma  
 
Güvenli sürümler kullanmak için kodu taşıma (sürümleriyle **_Yanları** soneki) CRT işlevleri, sonraki. Bu durumda, genel işlev ile değiştirilecek stratejisidir **_Yanları** sürüm ve daha sonra genellikle, gerekli ek arabellek boyutu parametreleri ekleyin. Boyut biliniyorsa bu yana çoğu durumda bu oldukça basittir. Burada boyutu hemen kullanılabilir değil, diğer durumlarda, bu CRT işlevi kullanarak işlev için ek parametreler eklemek gereklidir veya belki de hedef arabellek kullanımını inceleyin ve limitlerdir uygun boyutu bakın.  
  
Visual C++ kodu kadar boyutu parametresi eklemeden güvenli alma daha kolay hale getirmek için el sağlar ve şablon aşırı yüklemeleri kullanılarak olmasıdır. Bu aşırı yüklemeler şablonları olduğundan, ux'in için çalışmaz. Bu nedenle c Spyxxhk bir C projesi değil, yalnızca C++ derlenirken kullanıma sunuldu.  Ancak, Spyxx değil ve ux'in kullanabiliriz. Burada, her bir proje dosyasında gibi stdafx.h içinde derlenecek bir yerde şöyle bir satır eklemek için ux'in şöyledir:  
  
```cpp  
#define _CRT_SECURE_TEMPLATE_OVERLOADS 1  
```  
  
Arabellek bir dizi olduğunda, tanımladığınızda, dizi türünden çıkarılan bir ham işaretçi yerine boyutuna ve sağlaması gerek kalmadan boyutu parametresi kullanılan. Bu, kodu yeniden yazma karmaşıklığı kesmek için yardımcı olur. İşlevi adıyla değiştirilecek çözümlenmedi **_Yanları** sürümü, ancak genellikle göre arama yapılabilir ve işlem değiştirin.  
  
Bazı işlevler dönüş değerlerini değiştirildi. Örneğin, `_itoa_s` (ve `_itow_s` ve makro `_itot_s`) bir hata kodu döndürür (`errno_t`), dize yerine. Bu gibi durumlarda çağrı taşımak zorunda `_itoa_s` üzerine ayrı bir satır ve arabellek tanımlayıcısıyla değiştirin.  
  
Bazı genel örnekleri: için `memcpy`geçiş yaparken `memcpy_s`, kopyalanan yapının boyutunu sık ekledik. Benzer şekilde, çoğu dizeleri ve arabellekleri için dizi veya arabellek boyutunu kolayca öğesinden bildirim arabellek veya arabellek ilk ayrıldığı bulma tarafından belirlenir. Bazı durumlarda, büyük bir arabellek gerçekten edinilebilir ve bu bilgileri değişiklik yaptığınız, ek bir parametre olarak eklenmelidir ve çağıran kod şu şekilde değiştirilmelidir: işlev kapsamında kullanılabilir değilse, belirlemeniz gerekir. bilgi sağlar.  
  
Bu teknikler ile güvenli CRT işlevleri kullanmak için kodu dönüştürmek için yaklaşık yarım gün işlem. Değil şablon aşırı yüklemeleri ve boyutu parametreleri el ile eklemek için seçerseniz, iki kez veya üç kat daha fazla zaman büyük olasılıkla sürecektir.  
  
##  <a name="deprecated_forscope"></a> 13. adım. /ZC:forScope-kullanım dışıdır  
 
Visual C++ 6.0 bu yana derleyici döngü kapsamı için bir döngü içinde bildirilmiş değişkenlerin kapsamını sınırlar geçerli standardına uyar. Derleyici seçeneği [/ZC: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) (**döngü kapsamında uyumluluğu zorla** proje özelliklerinde) Bu hata olarak bildirilen olup olmadığını denetler. Biz kodumuz uyumlu olacak şekilde güncelleştirin ve hemen döngünün dışında bildirimleri ekleyin. Kod değişikliklerini yapmaktan kaçınmak için bu ayarı değiştirebilirsiniz **dil** için C++ proje özelliklerini bölümünü `No (/Zc:forScope-)`. Ancak, unutmayın `/Zc:forScope-` Visual C++'ın standart uyacak şekilde değiştirmek için kodunuzu gerekir, böylece sonunda gelecek sürümlerde kaldırılacak.  
  
Bu sorunları düzeltmek görece kolaydır, ancak kodunuzu bağlı olarak, bu kod etkileyebilir. Tipik bir sorun aşağıda verilmiştir.  
  
```cpp  
int CPerfTextDataBase::NumStrings(LPCTSTR mszStrings) const  
{  
  for (int n = 0; mszStrings[0] != 0; n++)  
  mszStrings = _tcschr(mszStrings, 0) + 1;  
  return(n);  
}    
```  
  
Yukarıdaki kod, bir hata oluşturur:  
  
```Output  
'n': undeclared identifier  
```  
  
Bu durum, derleyici artık C++ standardı ile uyumlu bir kod izin verilen bir derleyici seçeneği kullanım dışı kaynaklanır. Döngü dışında bir döngü sayacını kullanarak en yaygın uygulama sayacı bildirimini aşağıdaki yeniden düzenlenen kodu olduğu gibi döngünün dışında da taşınmasını gerektirir. Bu nedenle standart, bir döngü içinde bir değişken bildirme kapsamı yalnızca döngü için sınırlar :  
  
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
 
Spy ++ son derleyicinin özgün Visual C++ 6.0 kod taşıma zamanı çalıştıysa hakkında bir hafta içinde kodlama yaklaşık 20 saat sürdü. Sekiz sürümlerden ürünün Visual Studio 6.0 Visual Studio 2015 ile doğrudan yükseltildi. Artık tüm yükseltmelerde küçük ve büyük ölçekli projelerde önerilen yaklaşım budur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Taşıma ve yükseltme: örnekler ve örnek olay incelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)   
[Önceki örnek olay incelemesi: COM Spy](../porting/porting-guide-com-spy.md)