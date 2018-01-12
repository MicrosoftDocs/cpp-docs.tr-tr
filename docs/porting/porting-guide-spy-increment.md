---
title: "Taşıma Kılavuzu: Spy ++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: e558f759-3017-48a7-95a9-b5b779d5e51d
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 11b50aa8eb5c44a8949228d03b0b733de90fb0b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="porting-guide-spy"></a>Taşıma Kılavuzu: Spy++
Bu taşıma örnek olay incelemesi hangi tipik bir taşıma projede benzer bir fikir vermek üzere tasarlanmış, karşılaşabileceğiniz sorunları türlerini ve bazı genel ipuçları ve püf noktaları bağlantı noktası oluşturma sorunları ele almak için. Bu proje taşıma deneyimi kodu ayrıntılarını çok bağlı olduğundan bağlantı noktası oluşturma için eksiksiz bir kılavuz olma amacını değil.  
  
## <a name="spy"></a>Spy++  
 Spy ++ GUI yaygın olarak kullanılan bir tanılama aracı Windows masaüstünde, her türlü kullanıcı arabirimi öğeleri hakkında bilgi sağlayan Windows Masaüstü için değil. Windows tam hiyerarşisini gösterir ve her bir pencere ve Denetim hakkında meta verilerine erişim sağlar. Bu kullanışlı uygulama Visual Studio ile yıllardır sevk edilmiş. En son Visual C++ 6.0 ile derlenen ve Visual Studio 2015 için bağlantı noktası kurulmuş bir eski sürümü bulduk. Visual Studio 2017 deneyimini neredeyse aynı olmalıdır.
  
 Biz bu durumda her Visual C++ sürümünden bu yana Visual C++ 6.0 güncelleştirilmediği özellikle eski projeleri için MFC ve Win32 API kullanan Windows Masaüstü uygulamaları taşıma için tipik olarak kabul.  
  
##  <a name="convert_project_file"></a>1. adım. Proje dosyası dönüştürülüyor.  
 Visual C++ 6.0 iki eski .dsw dosyalarından proje dosyası kolayca daha fazla dikkat gerektiren herhangi bir sorun Yaşaması dönüştürülür. Bir proje Spy ++ uygulamasıdır. Diğer destekleyici DLL C'de yazılmış SpyHk olur. Daha karmaşık projeleri yükseltme gibi kolayca, ele alınan [burada](../porting/visual-cpp-porting-and-upgrading-guide.md).  
  
 İki proje yükselttikten sonra çözümümüzdür şöyle Aranan:  
  
 ![Spy &#43; &#43; Çözüm](../porting/media/spyxxsolution.PNG "SpyxxSolution")  
  
 Çok sayıda C++ dosyaları ve başka ile iki proje c dilinde yazılmış bir DLL sahibiz  
  
##  <a name="header_file_problems"></a>2. adım. Üstbilgi dosyası sorunları  
 Yeni dönüştürülmüş proje oluşturma sırasında genellikle bulabilirsiniz ilk şey projenizin kullandığı üstbilgi dosyaları bulunamadı biridir.  
  
 Spy ++ bulunamadı dosyalardan birini verstamp.h oluştu. Bir Internet aramadan bu eski veri teknolojisi bir DAO SDK'dan gelen belirledi. Hangi simgeleri bu başlığı dosyasından bu dosyayı gerçekten gerekirse veya üstbilgi dosyası bildirimi açıklamalı ve yeniden derlenmesi için bu simgeleri başka bir yerde tanımlanan görmek için kullanılan bulmak istedik. Ölçeklendiriyor renge gereklidir, tek bir simge VER_FILEFLAGSMASK.  
  
```  
1>C:\Program Files (x86)\Windows Kits\8.1\Include\shared\common.ver(212): error RC2104: undefined keyword or key name: VER_FILEFLAGSMASK  
```  
  
 Bul dosyaları (Ctrl + Shift + F) kullanın ve belirtmek için bir simge kullanılabilir içerme dosyaları bulmak için en kolay yolu olan **Visual C++ içerme dizinleri**. Biz ntverp.h bulundu. Biz verstamp.h yerini ntverp.h ile içerir ve bu hata kayboldu.  
  
##  <a name="linker_output_settings"></a>3. adım. Bağlayıcı ÇıktıDosyası ayarı  
 Eski projeleri bazen yükselttikten sonra sorunlara neden olabilecek sıra dışı konumlarda yerleştirilen dosyaları sahiptir. Bu durumda, biz $(SolutionDir) Visual Studio var. yerleştirilir bazı başlık dosyalarını bulabilmeniz için Proje Özellikleri'nde yerine Proje klasörlerden birinde INCLUDE yolu eklemeniz gerekir.  
  
 MSBuild Link.OutputFile özelliği TargetPath ve TargetName değerleri eşleşmiyor MSB8012 veren complains.  
  
```Output  
warning MSB8012: TargetPath(...\spyxx\spyxxhk\.\..\Debug\SpyxxHk.dll) does not match the Linker's OutputFile property value (...\spyxx\Debug\SpyHk55.dll). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).warning MSB8012: TargetName(SpyxxHk) does not match the Linker's OutputFile property value (SpyHk55). This may cause your project to build incorrectly. To correct this, please make sure that $(OutDir), $(TargetName) and $(TargetExt) property values match the value specified in %(Link.OutputFile).  
```  
  
 **Link.OutputFile** derleme çıktısı (EXE, DLL, örneğin) ve bu, normal olarak $(TargetDir)$(TargetName)$(TargetExt), yol ve dosya adı uzantısı vermiş oluşturulur. Eski Visual C++ projeleri geçirme Aracı (vcbuild.exe) derlerken yeni derleme aracını (MSBuild.exe) genel bir hata budur. Visual Studio 2010'yapı aracı değişiklik gerçekleştikten sonra bu bir pre-2010 project 2010'a geçirme her sorun veya sonraki bir sürümünü karşılaşabilirsiniz. Proje Yükseltme Sihirbazı'nı güncelleştirmez temel sorunu olan **Link.OutputFile** her zaman değeri olması gerektiğini belirlemek mümkün olmadığı değeri bir proje ayarlarınızı temel alan. Bu nedenle, genellikle el ile ayarlamanız gerekir. Daha fazla ayrıntı için bkz [sonrası](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx) Visual C++ blogunda.  
  
 Bu durumda, **Link.OutputFile** .\Debug\Spyxx.exe ve.\Release\Spyxx.exe Spy ++ proje için yapılandırmasına bağlı olarak ayarlandığından dönüştürülmüş projesinde özelliği. En iyi sonuç sadece bu sabit kodlanmış değerler ile $(TargetDir)$(TargetName)$(TargetExt) tüm yapılandırmalar için değiştirmektir. Bu işe yaramazsa, buradan özelleştirme, veya bu değerleri belirlendiği Genel bölümünde özelliklerini değiştirme (Özellikler **çıktı dizini**, **hedef adı**, ve  **Hedef uzantısı**. Görüntülemekte olduğunuz özelliği makroları kullanıyorsa, seçebileceğiniz unutmayın **Düzenle** yapılan makrosu değişimler ile son dizede gösteren bir iletişim kutusu açmak için aşağı açılan listesinde. Tüm kullanılabilir makroları ve geçerli değerleri seçerek görüntüleyebilirsiniz **makroları** düğmesi.  
  
##  <a name="updating_winver"></a>4. adım. Hedef Windows sürümü güncelleştiriliyor  
 Sonraki hata WINVER sürüm MFC'de artık desteklendiğini gösterir. Windows XP için WINVER 0x0501'i ' dir.  
  
```Output  
C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\atlmfc\include\afxv_w32.h(40): fatal error C1189: #error:  MFC does not support WINVER less than 0x0501.  Please change the definition of WINVER in your project properties or precompiled header.  
```  
  
 Visual Studio 2015'te, hedefleme izin olsa bile, destek uygulamalarınızda çıkışı aşamalandırılmasını ve yeni Windows sürümlerini benimsemek için kullanıcılarınızın görünümü teşvik eder Windows XP artık Microsoft tarafından desteklenir.  
  
 Hatadan kurtulmak için güncelleştirerek WINVER tanımlayın **proje özelliklerini** şu anda hedeflemek istediğiniz Windows en düşük sürüm olarak ayarlama. Çeşitli Windows sürümleri için değerlerinin tablosunu Bul [burada](http://msdn.microsoft.com/library/windows/desktop/aa383745.aspx).  
  
 Stdafx.h dosya bu makrosu tanımları bazıları içeriyor.  
  
```cpp  
#define WINVER       0x0500  // these defines are set so that we get the  
#define _WIN32_WINNT 0x0500  // maximum set of message/flag definitions,  
#define _WIN32_IE    0x0400  // from both winuser.h and commctrl.h.  
  
```  
  
 Windows 7'ye WINVER ayarlarız. Windows 7 (_WIN32_WINNT_WIN7) makrosu kullanırsanız kodu daha sonra değer kendisini (0x0601'i) yerine okuma daha kolaydır.  
  
```cpp  
#define WINVER _WINNT_WIN32_WIN7 // Minimum targeted Windows version is Windows 7  
```  
  
##  <a name="linker_errors"></a>5. adım. Bağlayıcı hataları  
 Bu değişiklikler ile SpyHk (DLL) projesini oluşturur, ancak bir bağlayıcı hata üretir.  
  
```  
LINK : warning LNK4216: Exported entry point _DLLEntryPoint@12  
```  
  
 Giriş noktası bir DLL için verilebilir. Giriş noktası, yalnızca diğer çağıranlar için dışarı aktarma tablosundaki olmamalıdır şekilde DLL'si belleğe ilk yüklendiğinde yükleyicisi tarafından çağrılması için tasarlanmıştır. Yalnızca bu yok emin olmak ihtiyacımız `__declspec(dllexport)` yönergesi ona bağlı. Spyxxhk.c şu iki yerlerden bildirim ve DLLEntryPoint tanımını kaldırmanız gerekir. Bu yönerge kullanmak için anlamlı hiçbir zaman yapılan ancak derleyici ve bağlayıcı önceki sürümlerinde, bir sorun olarak bayrak. Bağlayıcı'nın daha yeni sürümleri bir uyarı verir.  
  
```cpp  
// deleted __declspec(dllexport)  
BOOL WINAPI DLLEntryPoint(HINSTANCE hinstDLL,DWORD fdwReason, LPVOID lpvReserved);  
  
```  
  
 C DLL projesi, SpyHK.dll, şimdi oluşturur ve hatasız bağlar.  
  
##  <a name="outdated_header_files"></a>6. adım. Daha eski üstbilgi dosyaları  
 Bu noktada biz çalışmaya ana yürütülebilir projede, Spyxx başlatın.  
  
 Birkaç diğer dosyaları bulunamadı: ctl3d.h ve penwin.h. Bazen üstbilgi içereceği belirlemeye Internet aramak faydalı olabilir ancak bilgileri bu yararlı değildir. Biz ctl3d.h Exchange Geliştirme Seti parçası ve denetimlerinin Windows 95 belirli bir stil için destek sağlanan ve pencere kalem bilgi işlem için eski bir API penwin.h ilişkili olduğunu öğrenmiştir. Bu durumda, biz yalnızca çıkışı açıklama # satır include ve verstamp.h ile yaptığımız gibi tanımsız simgeleri ile ilgilidir. 3B denetimleri veya kalem Computing ilgili her şeyi projeden kaldırıldı.  
  
 Kademeli olarak ortadan birçok derleme hataları içeren bir proje göz önüne alındığında, bu hemen kaldırdığınızda eski bir API'nin tüm kullandığı bulmak için gerçekçi değildir #include yönergesi. Biz bu hemen, ancak bunun yerine bir noktada algılamadı noktaya gelen WM_DLGBORDER tanımlanmamış bir hata oluştu. Gerçekte yalnızca biri olan birçok tanımsız ctl3d.h gelen simgeler. Biz eski API'ye ilişkili saptadıktan sonra bu kodu biz tüm başvurular kaldırıldı.  
  
##  <a name="updating_iostreams_code"></a>7. adım. Eski iostreams kodunu güncelleme  
 Sonraki hata iostreams kullanan eski C++ kodu ile yaygındır.  
  
 mstream.h(40): önemli bir hata C1083: açık dosya içeremez: 'iostream.h': böyle dosya veya dizin yok  
  
 Eski iostreams kitaplığı kaldırıldı ve yerini işlemidir. Eski iostreams yeni standartları ile değiştirmek sahip.  
  
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
  
 Bu değişiklikle, artık kullanılmayan ostrstream sorunlara sahip. Uygun yerini ostringstream alır. Ostrstream kodunda değişiklik çok büyük bir başlangıç en az önlemek için bir typedef eklemeyi deneyin.  
  
```cpp  
typedef std::basic_ostringstream<TCHAR> ostrstream;  
  
```  
  
 Şu anda proje MBCS (çok baytlı karakter kümesi), char uygun karakter veri türü olacak şekilde kullanarak oluşturuyor. Ancak, daha kolay bir güncelleştirme UTF-16 Unicode koda izin vermek için bu char veya wchar_t mı bağlı olarak çözümler TCHAR için güncelleştiriyoruz **karakter kümesi** proje ayarlarını özellik MBCS veya Unicode olarak ayarlanmış.  
  
 Birkaç kod parçalarını güncelleştirilmesi gerekir.  Biz temel sınıf ios ios_base ile değiştirilir ve biz ostream değiştirilir tarafından basic_ostream olan\<T >. İki ek tür tanımları eklediğimiz ve bu bölümde derler.  
  
```cpp  
typedef std::basic_ostream<TCHAR> ostream;  
typedef ios_base ios;  
  
```  
  
 Bu tür tanımları yalnızca geçici bir çözüm kullanmaktır. Daha fazla kalıcı bir çözüm için biz her yeniden adlandırılmış veya güncel API başvuru güncelleştirebilir.  
  
 Burada, sonraki hata verilmiştir.  
  
```Output  
error C2039: 'freeze': is not a member of 'std::basic_stringbuf<char,std::char_traits<char>,std::allocator<char>>'  
```  
  
 Bu basic_stringbuf dondurma yöntemi yok sonraki sorunudur. Freeze yöntemi, bir bellek sızıntısı eski ostream önlemek için kullanılır. Yeni ostringstream kullanmakta olduğunuz göre biz ihtiyacınız yoktur. Biz donmasına çağrı silebilirsiniz.  
  
```cpp  
//rdbuf()->freeze(0);  
```  
  
 Bitişik satırlarında sonraki iki hatalar oluştu. İlk sona erdiğinde kullanma hakkında bir null Sonlandırıcı dizesi eski iostream kitaplığının g/ç manipulator olduğu complains.  Str yöntemi çıktısını const olmayan işaretçi atanan bu hataların ikinci açıklanmaktadır.  
  
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
  
 Yeni akış kitaplığını kullanarak, uçları gerekmiyor satır kaldırılabilir böylece dize her zaman null ile sonlandırılmış, olduğundan. Bir dizeyi karakter dizisine bir işaretçi Str() döndürmez artık ikinci sorun için sorunu olan; std::string türü döndürür. İkinci çözüm için LPCSTR türünü değiştirin ve işaretçiyi istemek için c_str() yöntemi kullanmaktır.  
  
```cpp  
//*this << ends;  
LPCTSTR psz = str().c_str();  
  
```  
  
 Bize biraz puzzled bir hata oluştu. Bu kodu.  
  
```cpp  
MOUT << _T(" chUser:'") << chUser  
<< _T("' (") << (INT)(UCHAR)chUser << _T(')');  
  
```  
  
 Makro `MOUT` çözümler * türünde bir nesne olan g_pmout `mstream`. Standart çıktı dize sınıfından türetilen mstream sınıfı `std::basic_ostream<TCHAR>.` ancak biz Unicode'a işleci aşırı yükleme çözümü dönüştürmek için hazırlık koyun _T dize sabit değeri, geçici ile << şu hatayı vererek başarısız olur İleti:  
  
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
  
 Çok fazla sayıda işleci vardır << tanımları bu tür bir hatayı göz korkutucu olabilir. Kullanılabilir aşırı daha yakından arayan bunların çoğu ilgisiz ve daha yakından adresindeki görünümlü görebiliriz `mstream` sınıf tanımının çağrılabilir bu durumda düşünüyoruz aşağıdaki işlevi belirledik.  
  
```cpp  
mstream& operator<<(LPTSTR psz)  
{  
  return (mstream&)ostrstream::operator<<(psz);  
}  
  
```  
  
 Değişmez değer dize türü olduğundan değil olarak adlandırılan bir nedeni `const wchar_t[10]` o uzun hata iletisi son satırından gördüğünüz gibi bu nedenle dönüştürme const olmayan işaretçisi değil otomatik. Daha uygun parametre türü LPCTSTR gelir ancak işleç giriş parametresi değiştirmemeniz gerekir (`const char*` MBCS derlerken ve `const wchar_t*` Unicode olarak), değil LPTSTR (`char*` MBCS derlerken ve `wchar_t*` olarak Unicode). Bu değişikliği yapmadan bu hatayı düzeltir.  
  
 Bu tür dönüştürme altında daha eski, daha az kesin derleyici izin ancak daha yeni uyum değişiklik daha doğru kodu gerektirir.  
  
##  <a name="stricter_conversions"></a>8. adım. Derleyicinin daha katı dönüşümleri  
 Biz de aşağıdaki gibi birçok hata alırsınız:  
  
```  
error C2440: 'static_cast': cannot convert from 'UINT (__thiscall CHotLinkCtrl::* )(CPoint)' to 'LRESULT (__thiscall CWnd::* )(CPoint)'  
```  
  
 Hata iletisi eşlemde yalnızca bir makro oluşur:  
  
```cpp  
BEGIN_MESSAGE_MAP(CFindToolIcon, CWnd)  
// other messages omitted...  
ON_WM_NCHITTEST() // Error occurs on this line.  
END_MESSAGE_MAP()  
```  
  
 Bu makrosu tanımına giderek, biz OnNcHitTest işlevi başvurduğu bakın.  
  
```cpp  
#define ON_WM_NCHITTEST() \  
{ WM_NCHITTEST, 0, 0, 0, AfxSig_l_p, \  
(AFX_PMSG)(AFX_PMSGW) \  
(static_cast< LRESULT (AFX_MSG_CALL CWnd::*)(CPoint) > (&ThisClass :: OnNcHitTest)) },  
```  
  
 Üye işlev türleri işaretçisine uyuşmazlık ile yapmak sorun vardır. Geçerli bir base ile türetilmiş dönüştürme olduğundan sorun dönüştürme CHotLinkCtrl öğesinden bir sınıf türü olarak CWnd sınıfı türü değil. Dönüş türü sorunudur: UINT vs. LRESULT. UINT bu türe dönüştürme değil, bir 64-bit işaretçi ya da hedef ikili türüne bağlı olarak bir 32 bit işaretçi olan LONG_PTR LRESULT çözümler. Bu çok sayıda ileti eşlemesi yöntemleri dönüş türü UINT Visual Studio 2005'te LRESULT için 64-bit uyumluluk değişiklikleri bir parçası olarak değiştiğinden 2005'ten önce yazılan kod yükseltirken seyrek değildir. Dönüş türü biz LRESULT için tek tek aşağıdaki kodda UINT değiştirin:  
  
```cpp  
afx_msg UINT OnNcHitTest(CPoint point);  
```  
  
 Değişiklikten sonra aşağıdaki kodu vardır:  
  
```cpp  
afx_msg LRESULT OnNcHitTest(CPoint point);  
```  
  
 CWnd türetilen tüm farklı sınıflardaki bu işlev yaklaşık on oluşumları olduğundan kullanmak yararlı **Tanıma Git** (klavye: F12) ve **bildirimine Git** (klavye: Ctrl + F12) olduğunda İmleç işlevi bu bulun ve gezinmek için düzenleyicisinde gelen onlara **Find Symbol** araç penceresi. **Tanımı gidin** genellikle daha iki yararlıdır. **Bildirim gidin** tanımlama dışında Bul bildirimleri sınıf bildiriminin arkadaş sınıf bildirimleri gibi veya İleri başvuruları.  
  
##  <a name="mfc_changes"></a>9. adım. MFC değişiklikleri  
 Sonraki hata da değiştirilen bildirim türüne ilgilidir ve ayrıca makro oluşur.  
  
```Output  
error C2440: 'static_cast': cannot convert from 'void (__thiscall CFindWindowDlg::* )(BOOL,HTASK)' to 'void (__thiscall CWnd::* )(BOOL,DWORD)'  
```  
  
 Sorun CWnd::OnActivateApp ikinci parametre için DWORD HTASK değiştirilmiş olmasıdır. Visual Studio, Visual Studio .NET 2002 sürümünde bu değişikliği oluştu.  
  
```cpp  
afx_msg void OnActivateApp(BOOL bActive, HTASK hTask);  
```  
  
 Türetilen sınıflar OnActivateApp bildirimlerinde uygun şekilde aşağıdaki gibi güncelleştirmeye vardır:  
  
```cpp  
afx_msg void OnActivateApp(BOOL bActive, DWORD dwThreadId);  
```  
  
 Bu noktada, biz Projeyi derlemek kullanabilirsiniz. Ancak, üzerinden çalışmak için birkaç uyarıları vardır ve MBCS Unicode dönüştürme veya güvenli CRT işlevleri kullanarak güvenlik artırma gibi yükseltme, isteğe bağlı bölümleri vardır.  
  
##  <a name="compiler_warnings"></a>10. adım. Adresleme derleyici uyarıları  
 Uyarıların tam bir listesini almak için yapmanız bir **yeniden tüm** uyarı raporları yalnızca geçerli aldığından çözümü yerine sıradan bir yapı, yalnızca emin olmak için bu her şeyi önceden derlenmiş, derlenecek derleme. Diğer soru geçerli uyarı düzeyi kabul etmek veya daha yüksek bir uyarı düzeyi kullanmayı ' dir.  Çok fazla kod, özellikle eski kod bağlantı noktası oluşturma, daha yüksek bir uyarı düzeyi kullanarak uygun olabilir.  Varsayılan uyarı düzeyi ile başlayıp tüm uyarıları almak için uyarı düzeyini artırmak isteyebilirsiniz. Wln kullanıyorsanız, bazı uyarılar sistemde üstbilgi dosyaları almak için sistem üstbilgileri için uyarılar almadan kendi kodlarına çoğu uyarıları almak için çok fazla kişi /W4 kullanır. Uyarıları hata olarak görünmesini istiyorsanız /WX seçeneği ekleyin. Bu ayarlar Proje Özellikleri iletişim kutusu C/C++ bölümünde yer alır.  
  
 CSpyApp sınıftaki yöntemlerin birini artık desteklenmeyen bir işlev hakkında bir uyarı üretir.  
  
```cpp  
void SetDialogBkColor() {CWinApp::SetDialogBkColor(::GetSysColor(COLOR_BTNFACE));}  
```  
  
 Uyarı aşağıdaki gibidir.  
  
```Output  
warning C4996: 'CWinApp::SetDialogBkColor': CWinApp::SetDialogBkColor is no longer supported. Instead, handle WM_CTLCOLORDLG in your dialog  
```  
  
 Artık gerekli olmadığında SetDialogBkColor yönelik tüm başvuruları silmek için gereken tek değişiklik şekilde WM_CTLCOLORDLG ileti Spy ++ kodunda, zaten işlendi.  
  
 Sonraki uyarı değişken adı yorum tarafından düzeltmek kolay. Aşağıdaki uyarı aldık:  
  
```Output  
warning C4456: declaration of 'lpszBuffer' hides previous local declaration  
```  
  
 Bu üreten kod makro içerir.  
  
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
  
 Bu kod olduğu gibi makroları kullanımına ağırlık Kodu'nu korumak daha zor eğilimindedir. Bu durumda, makroları değişkenleri bildirimlerini içerir. Parametre makrosu şu şekilde tanımlanır:  
  
```cpp  
#define PARM(var, type, src)type var = (type)src  
```  
  
 Bu nedenle lpszBuffer değişkeni iki kere aynı işlevinde bildirimi. Kod olan kullanmıyorsa, makroları (yalnızca ikinci türü bildirimi kaldırma) olduğu gibi bu sorunu gidermek için bu straightfoward değil. Olduğu gibi biz makro kodunu sıradan kodu (yorucu ve büyük olasılıkla hataya görev) olarak yeniden yazın veya uyarıyı devre dışı bırak karar gerek kalmadan talihsiz seçeneğiniz vardır.  
  
 Bu durumda, biz uyarıyı devre dışı bırakmak için iptal et. Pragma gibi ekleyerek bunu:  
  
```cpp  
#pragma warning(disable : 4456)  
```  
  
 Bir uyarı devre dışı bırakılırken devre dışı bırakma sınırlamak isteyebilirsiniz olan kodu için yararlı bilgiler sağlayabilir olduğunda uyarı gizleme önlemek için uyarı üreten etkilemek. Biz yalnızca bu üretir satırından sonra uyarı geri yüklemek için kodu ekleyin veya makro, bu uyarıyı oluşur daha iyi henüz kullanamadı `__pragma` makroları çalışır anahtar sözcüğü (`#pragma` içindeki makrolar çalışmıyor).  
  
```cpp  
#define PARM(var, type, src)__pragma(warning(disable : 4456))  \  
type var = (type)src \  
__pragma(warning(default : 4456))  
  
```  
  
 Sonraki uyarı bazı kod sürümlerini gerektirir. Win32 API GetVersion (ve GetVersionEx) kullanım dışıdır.  
  
```Output  
warning C4996: 'GetVersion': was declared deprecated  
```  
  
 Aşağıdaki kod sürümü nasıl elde gösterir.  
  
```cpp  
// check Windows version and set m_bIsWindows9x/m_bIsWindows4x/m_bIsWindows5x flags accordingly.  
DWORD dwWindowsVersion = GetVersion();  
  
```  
  
 Bu, çok fazla biz Windows 95'te çalışmakta olduğunuzdan belirlemek için dwWindowsVersion değeri inceler kod ve Windows NT hangi sürümü tarafından izlenir. Tüm eski olduğundan, biz kodunu kaldırmak ve tüm başvuruları değişkenlere uğraşmanız.  
  
 Makaleyi [Windows 8.1 ve Windows Server 2012 R2 işletim sistemi sürüm yapılan değişiklikleri](https://msdn.microsoft.com/library/windows/desktop/dn302074.aspx) durum açıklanmaktadır.  
  
 İşletim sistemi sürümü sorgu CSpyApp sınıftaki yöntemlerin vardır: IsWindows9x, IsWindows4x ve IsWindows5x. Şu ana kadar bu eski uygulama tarafından kullanılan teknoloji olarak Windows NT 5 kaygı biz (Windows 7 ve üzeri) desteklemek istediğiniz Windows sürümlerini kapatmak için tüm gereken iyi bir başlangıç noktası edileceğidir. Eski işletim sistemlerini kısıtlamalarla mücadele etmek için bu yöntemlerin kullandığı yoktu. Bu nedenle TRUE ve FALSE IsWindows5x için başkalarının döndürmek için bu yöntemi değişti.  
  
```cpp  
BOOL IsWindows9x() {/*return(m_bIsWindows9x);*/ return FALSE;  }  
BOOL IsWindows4x() {/*return(m_bIsWindows4x);*/ return FALSE;  }  
BOOL IsWindows5x() {/*return(m_bIsWindows5x);*/ return TRUE;  }  
  
```  
  
 Yalnızca iç değişkenler doğrudan kullanıldığı birkaç yerler sol. Biz bu değişkenleri kaldırılmış olduğundan, biz açıkça uğraşmanız gereken birkaç hatayla karşılaşıyorsunuz.  
  
```Output  
error C2065: 'm_bIsWindows9x': undeclared identifier  
```  
  
```cpp  
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)  
{  
  pCmdUI->Enable(m_bIsWindows9x || hToolhelp32 != NULL);  
}  
  
```  
  
 Biz bunu bir yöntem çağrısı veya yalnızca geçişi doğru değiştirin ve eski özel durum Windows 9 kaldırın x.  
  
```cpp  
void CSpyApp::OnUpdateSpyProcesses(CCmdUI *pCmdUI)  
{  
  pCmdUI->Enable(TRUE /*!m_bIsWindows9x || hToolhelp32 != NULL*/);  
}  
  
```  
  
 Son uyarı varsayılan düzeyde (3) saklayıcısında ile ilgilidir.  
  
```Output  
treectl.cpp(1656): warning C4463: overflow; assigning 1 to bit-field that can only hold values from -1 to 0  
```  
  
 Bu tetikler kod aşağıdaki gibidir.  
  
```cpp  
m_bStdMouse = TRUE;  
```  
  
 M_bStdMouse bildirimi, bir saklayıcısında olduğunu gösterir.  
  
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
  
 Bu kod, yerleşik bool türü Visual C++'da desteklenen önce yazıldı. Bu tür kodda BOOL typedef tamsayı için oluştu. İnt türü işaretli bir türe ve imzalı int bit gösterimini saklayıcısında int türü temsil eden, 0 veya büyük olasılıkla ne tasarlanmıştır -1 olarak yorumlanabilecek şekilde ilk bit oturum bit kullanılacak.  
  
 Koda bakarak bildiğiniz olmayacaktır bit alanları bunlar neden. Nesnesinin boyutunu küçük tutmaya hedefi olan ya da mevcut herhangi bir yere nesne ikili düzenini nerede kullanılır? Bir saklayıcısında kullanımı için herhangi bir nedenle görmek istemediğiniz beri Biz bu sıradan BOOL üyelerine değiştirildi. Bir nesnenin boyutunu küçük tutmak için bit alanları kullanarak çalışmaya garantisi yoktur. Bu derleyici türü nasıl yerleştirir bağlıdır.  
  
 Standart türü bool boyunca kullanarak yararlı olacaktır, merak ediyor. BOOL türü gibi eski kod düzenleri çoğunu BOOL bool yerleşik türü değiştirmek bu tür bir değişiklik yalnızca bir örneği başlangıçta çalıştıran kodunuzu aldıktan sonra yaparken göz önünde bulundurun, böylece daha sonra standart C++'da, çözüldü sorunları çözmek için invented yeni sürümde.  
  
 Biz varsayılan düzeyde (Düzey 3) görünen tüm uyarıları ile ele sonra sabit düzey birkaç ek uyarıları yakalamak için 4 değiştirdik. Aşağıdaki gibi görünen ilk oluştu:  
  
```Output  
warning C4100: 'nTab': unreferenced formal parameter  
```  
  
 Bu uyarı üretilen kod şu şekilde oluştu.  
  
```cpp  
virtual void OnSelectTab(int nTab) {};  
```  
  
 Bu yetecek zararsız gibi görünüyor, ancak biz /W4 ve /WX kümesiyle temiz bir derleme istedik olduğundan, biz yalnızca değişken adı amacıyla okunabilirlik bırakarak açıklamalı.  
  
```cpp  
virtual void OnSelectTab(int /*nTab*/) {};  
```  
  
 Aldığımız diğer uyarılara genel kod Temizleme için yararlıdır. Örtük dönüşümler bir dizi vardır `int` veya `unsigned int` için `WORD` (için typedef olduğu `unsigned short`). Bu olası veri kaybını içerir. Bir cast eklediğimiz `WORD` bu durumda.  
  
 Biz bu kodu için var olan başka bir düzey 4 uyarı oluştu:  
  
```Output  
warning C4211: nonstandard extension used: redefined extern to static  
```  
  
 Bir değişken ilk bildirildi sorun oluşur `extern`, daha sonra bildirilen `static`. Bu iki depolama sınıfı tanımlayıcıları anlamını birbirini dışlayan, ancak bu bir Microsoft uzantısı olarak izin verilir. Kodunun diğer derleyiciler taşınabilir olmasını istediğiniz ya da /Za (ANSI uyumluluğu) ile derlemek istedi, eşleşen depolama sınıfı tanımlayıcıları için bildirimler değiştirirsiniz.  
  
##  <a name="porting_to_unicode"></a>11. adım. Unicode MBCS bağlantı noktası oluşturma  
 Unicode dediğimiz Windows dünyasında, biz genellikle UTF-16 anlama olduğunu unutmayın. UTF-8 Linux gibi diğer işletim sistemlerinin kullanın, ancak Windows bir genellikle desteklemez. Gerçekte UTF-16 Unicode MBCS koda bağlantı noktası için adımı gerçekleştirmeden önce geçici olarak MBCS kullanım dışıdır uyarılarını kaldırmak için diğer iş yapmak veya bunları taşıma uygun bir zamana kadar erteleyin için istiyoruz. MBCS geçerli kod kullanır ve MFC MBCS sürümünü indirmek ihtiyacımız devam etmek için.  Ayrı olarak indirilmesi gerekir böylece bu yerine büyük kitaplığı varsayılan Visual Studio yüklemesinden kaldırıldı. Bkz: [MFC MBCS DLL eklentisi](../mfc/mfc-mbcs-dll-add-on.md). Bu karşıdan yükleyip Visual Studio'yu yeniden başlatın sonra derlemek ve MFC MBCS sürümü ile bağlantı ancak MBCS hakkında uyarılar kurtulmak için de NO_WARN_MBCS_MFC_DEPRECATION proje önişlemci bölümünde önceden tanımlı makrolar listesine eklemeniz özellikleri veya stdafx.h üstbilgi dosyası veya diğer ortak üstbilgi dosyası başlangıcı.  
  
 Şimdi bazı bağlayıcı hatalarını sunuyoruz.  
  
```Output  
fatal error LNK1181: cannot open input file 'mfc42d.lib'  
```  
  
 Mfc eski statik kitaplık sürümünü giriş bağlayıcı üzerinde yer aldığından LNK1181 oluşur. Artık biz MFC dinamik olarak bağlayabilirsiniz beri yalnızca giriş özellik Proje Özellikleri'nin bağlayıcı bölümdeki tüm MFC statik kitaplıklar kaldırmak ihtiyacımız şekilde bu gerekli değildir. Bu proje /NODEFAULTLIB seçeneği de kullanıyor ve bunun yerine tüm kitaplık bağımlılıkları listeler.  
  
```  
msvcrtd.lib;msvcirtd.lib;kernel32.lib;user32.lib;gdi32.lib;advapi32.lib;Debug\SpyHk55.lib;%(AdditionalDependencies)  
```  
  
 Artık bize gerçekte eski çok baytlı karakter kümesi (MBCS) kodu Unicode'a güncelleştirin. Bu içkin şekilde Windows masaüstü platformu için bağlı olan bir Windows uygulaması olduğundan biz bunu UTF-16 Unicode için Windows'un kullandığı bağlantı noktası. Platformlar arası kod yazma veya başka bir platform için bir Windows uygulaması bağlantı noktası oluşturma, diğer işletim sistemlerinde yaygın olarak kullanılan UTF-8 bağlantı noktası oluşturma düşünmek isteyebilirsiniz.  
  
 UTF-16 Unicode için bağlantı noktası oluşturma, biz biz yine MBCS'den veya derleme seçeneği isteyip istemediğinize karar gerekir.  MBCS Desteği seçeneğine sahip istiyoruz, biz TCHAR makrosu char veya wchar_t olup derleme sırasında _MBCS veya _UNICODE tanımlanan bağlı olarak, çözülen karakter türü olarak kullanmanız gerekir. TCHAR ve TCHAR wchar_t yerine çeşitli API'ler ve ilişkili API'ler sürümleri geçiş yapma, geri kodunuzu MBCS sürüme _MBCS makrosu _UNICODE yerine tanımlayarak edinebileceğiniz anlamına gelir. TCHAR yanı sıra, yaygın olarak kullanılan tür tanımları, makrolar ve işlevler gibi TCHAR sürümlerini çeşitli bulunmaktadır. Örneğin, LPCSTR ve benzeri yerine LPCTSTR. Proje Özellikleri iletişim kutusunda, altında **yapılandırma özellikleri**, **genel** bölümünde **karakter kümesi** özelliğinden **kullanım MBCS Karakter kümesi** için **Unicode karakter kümesi kullanan**. Bu ayar, hangi makrosu derleme sırasında önceden tanımlanmış etkiler. UNICODE makrosu ve _UNICODE makrosu yoktur. Proje özelliği hem de tutarlı bir şekilde etkiler. Visual C++ üstbilgi MFC gibi _UNICODE kullandığınızda, ancak bir tanımlandığında Windows üstbilgileri UNICODE kullanın, diğer her zaman tanımlanır.  
  
 İyi bir [Kılavuzu](http://msdn.microsoft.com/library/cc194801.aspx) UTF-16 Unicode'a MBCS bağlantı noktası oluşturma için TCHAR kullanarak mevcut. Biz bu yol seçin. İlk olarak, biz değiştirmek **karakter kümesi** özelliğine **kullanım Unicode karakter kümesi** ve projeyi yeniden derleyin.  
  
 Kodda yerler zaten kullanmakta olduğunuz `TCHAR`, sonunda Unicode destekleme görünüşe göre kapatıldığını. Bazı değildi. Biz arama örneklerini `CHAR`, char ve bunların TCHAR ile değiştirilen çoğu için typedef olduğu. Ayrıca, şu arama `sizeof (CHAR)`. Sabit değiştirdik her `CHAR` için `TCHAR`, biz genellikle değiştirmek zorunda `sizeof(TCHAR)` bu genellikle bir dizedeki karakter sayısını belirlemek için kullanılan bu yana. Bu durumda dikkat biraz ödeme değer olacak şekilde yanlış türde burada kullanarak derleyici hatası üretmez.  
  
 Bu tür hatalara Unicode'a değiştirdikten sonra çok yaygındır.  
  
```Output  
error C2664: 'int wsprintfW(LPWSTR,LPCWSTR,...)': cannot convert argument 1 from 'CHAR [16]' to 'LPWSTR'  
```  
  
 Burada, bu üreten kod örneği verilmiştir:  
  
```cpp  
wsprintf(szTmp, "%d.%2.2d.%4.4d", rmj, rmm, rup);  
```  
  
 Biz _T dize geçici hata kaldırmak için değişmez değer yerleştirin.  
  
```cpp  
wsprintf(szTmp, _T("%d.%2.2d.%4.4d"), rmj, rmm, rup);  
```  
  
 _T makrosu bir karakter veya UNICODE ve MBCS ayarı bağlı olarak bir wchar_t dize olarak bir dize sabit değeri derleme yapma etkisi yoktur. _T Visual Studio ile tüm dizeleri değiştirmek için önce açın **hızlı Değiştir** (klavye: Ctrl + F) kutusunu veya **dosyalarda Değiştir** (klavye: Ctrl + Shift + H), ardından **kullanım normal İfadeleri** onay kutusu. Girin `((\".*?\")|('.+?'))` arama metni olarak ve `_T($1)` değiştirme metin olarak. Bazı dizelerini geçici _T makrosu zaten varsa, bu yordamı, yeniden ekleyecek ve burada istemediğiniz kullandığınızda gibi _T durumlarda bulabilirsiniz `#include`, kullanmak en iyisidir **Değiştir sonraki** yerine  **Tüm değiştirmek**.  
  
 Bu belirli işlevi [wsprintf](https://msdn.microsoft.com/library/windows/desktop/ms647550.aspx), bu, olası arabellek taşması nedeniyle kullanılmaması önerir için gerçekten Windows üstbilgileri ve belgelere tanımlanır. Boyut için verilen `szTmp` arabellek arabellek için yazılacak tüm verileri tutabilir denetlemek işlev için hiçbir şekilde gelir. Güvenli biz benzer diğer sorunları gidermek CRT için bağlantı noktası oluşturma hakkında sonraki bölüme bakın. İle değiştirerek sona [_stprintf_s](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md).  
  
 Unicode dönüştürme görürsünüz başka bir ortak hata budur.  
  
```Output  
error C2440: '=': cannot convert from 'char *' to 'TCHAR *'  
```  
  
 Bu üretir kod aşağıdaki gibidir:  
  
```cpp  
pParentNode->m_szText = new char[strTitle.GetLength() + 1];  
_tcscpy(pParentNode->m_szText, strTitle);  
  
```  
  
 _Tcscpy işlevi, bir dize kopyalama TCHAR strcpy işlevi olan kullanılan olsa bile, ayrılan arabellek char arabelleği. Bu TCHAR için kolayca değiştirilir.  
  
```cpp  
pParentNode->m_szText = new TCHAR[strTitle.GetLength() + 1];  
_tcscpy(pParentNode->m_szText, strTitle);  
  
```  
  
 Benzer şekilde, sabit değiştirdik `LPSTR` (dizeye uzun işaretçisi) ve `LPCSTR` (sabit dizeye uzun işaretçisi) için `LPTSTR` (TCHAR dizeye uzun işaretçisi) ve `LPCTSTR` (sabit TCHAR dizeye uzun işaretçisi) sırasıyla tarafından garanti olduğunda bir Derleyici Hatası. Her durumda, ayrı ayrı incelenmesi gerekiyordu çünkü bu tür değişiklik genel Ara ve Değiştir ' kullanarak yapmamak seçtik. Bazı durumlarda, char sürümü, ne zaman belirli Windows A son ekine sahip Windows yapıları kullandığınız iletilerini işleme gibi istenmeyen. Windows API içinde bir sonek ASCII veya ANSI anlamına gelir (ve MBCS için de geçerlidir) ve geniş karakterler veya UTF-16 Unicode W soneki anlamına gelir. Bu adlandırma deseni Windows üstbilgilerinde kullanılır, ancak yalnızca bir MBCS sürümde zaten tanımlı bir işlev Unicode sürümünü eklemek varken de onu Spy ++ kodunda izlenen.  
  
 Biz doğru çözümleyen bir sürümünü kullanmak için bir tür değiştirmek zorunda bazı durumlarda (örneğin WNDCLASSA yerine WNDCLASS).  
  
 Çoğu durumda biz Win32 API GetClassName (yerine GetClassNameA) gibi genel sürümünü (makrosu) kullanmanız gerekiyordu. İleti işleyicisi SWITCH deyiminde bazı iletiler MBCS veya Unicode belirli, bu durumda, biz biz W belirli işlevler ve genel olarak adlandırılmış işlevleri A ile değiştirilir ve makro eklenen çünkü MBCS sürümünü açıkça çağırmak için kodu değiştirmek zorunda kaldı doğru A çözümler genel adı veya UNICODE tanımlanan üzerinde temel W adı.  _UNICODE, tanımlamak için yaptık zaman kodu birçok bölümlerini W sürümü artık sürümünü ne istedik olduğunda bile seçilir.  
  
 Özel Eylemler burada alınması gerekiyordu birkaç yer vardır. Tüm WideCharToMultiByte veya MultiByteToWideChar daha yakından kullanımını gerektirebilir. Burada, burada WideCharToMultiByte kullanılan bir örnek verilmiştir.  
  
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
  
 Bu sorunu çözmek için şu işlemi yapılmıştı neden bir CString strFace iç arabelleğine yazı tipinin adını temsil eden bir geniş karakter dizesi kopyalama olduğunu anlamak zorunda kalındı. Bu durumda eklediğimiz bir #ifdef şekilde bu biraz farklı kod geniş karakter CString dizeleri için olduğu gibi birden çok baytlı CString dizeleri için gereklidir.  
  
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
  
 Elbette, yerine wcscpy biz gerçekten wcscpy_s, daha güvenli bir sürümünü kullanmanız gerekir. Sonraki bölümde bu giderir.  
  
 Bizim iş bir onay, şu karakter kümesi kullanım çok baytlı karakter kümesi için sıfırlama ve Unicode yanı sıra MBCS kullanan kodu hala derlendiğinden emin olun gerekir. Needless çok deyin tam test geçişi bu değişikliklerden sonra derlenmiş uygulama üzerinde yürütülmelidir.  
  
 Bu Spy ++ çözüm bizim iş Unicode kod dönüştürmek ortalama bir C++ Geliştirici için yaklaşık iki çalışma günleri sürdü. Retesting zaman içermiyordu.  
  
##  <a name="porting_to_secure_crt"></a>12. adımı. Güvenli CRT kullanılacak bağlantı noktası oluşturma  
 CRT işlevlerinin güvenli sürümleri (_Yanları sonekiyle sürümler) kullanmak için kodu taşıma sonraki. Bu durumda, genel stratejisi işlevi _Yanları sürümle ve ardından, genellikle, gerekli olan ek arabellek boyutu parametreleri eklemektir. Boyutu bilinen beri çoğu durumda bu basittir. Diğer durumlarda, burada boyutu hemen kullanılabilir değil, bu CRT işlevini kullanarak işlev için ek parametreler eklemek gerekli olan veya belki de hedef arabellek kullanımını inceleyin ve limitleri uygun boyutu bakın.  
  
 Visual C++ sayıda boyutu parametreleri eklemeden kod güvenli daha kolay yapmak için bir çözüm sağlar ve şablon aşırı yüklemeleri kullanarak olmasıdır. Bu aşırı şablonları olduğundan, eli için çalışmaz C. Spyxxhk C proje olmadığından gibi bunlar yalnızca C++ derlerken kullanılabilir.  Ancak, Spyxx değil ve eli kullanırız. Burada, her proje dosyasında gibi Stdafx.h'de derlenecek bir yerde şuna benzer bir satır eklemek için eli şöyledir:  
  
```cpp  
#define _CRT_SECURE_TEMPLATE_OVERLOADS 1  
```  
  
 Arabellek bir dizi olduğunda, tanımladığınızda, ham bir işaretçi yerine boyutuna dizi türünden algılanır ve onu tedarik gerek kalmadan boyutu parametresi kullanılan. Kodu yeniden yazma karmaşıklığını kesme yardımcı olan. İşlev adı _Yanları sürümüyle değiştirmek hala sahip, ancak genellikle göre arama yapılabilir ve işlem değiştirin.  
  
 Bazı işlevler dönüş değerleri değiştirildi. Örneğin, _itoa_s (ve _itow_s ve makrosu _itot_s) bir hata kodu (errno_t) yerine dize döndürür. Bu durumda, ayrı bir satırda üzerine _itoa_s çağrısı taşımak ve arabellek tanımlayıcısıyla değiştirmek sahip şekilde.  
  
 Bazı ortak durumları: memcpy_s için geçiş yaparken memcpy için, sık kopyalanan yapısı boyutunu eklediğimiz. Benzer şekilde, çoğu dizeler ve arabellekleri için dizi veya arabellek boyutu kolayca arabellek veya burada arabellek başlangıçta ayrıldı bulma tarafından bildirimi gelen belirlenir. Bazı durumlarda, büyük bir arabellek gerçekte nasıl edinilebilir ve bu bilgileri değişiklik yaptığınız, ek bir parametre eklenmesi gerektiğini ve çağrıyı yapan kod değiştirilmesi gerektiğini işlev kapsamında yoksa belirlemeniz gerekir. bilgileri sağlayın.  
  
 Bu teknikler ile güvenli CRT işlevleri kullanmak için kodu dönüştürmek için yaklaşık yarım gün sürdü. Değil şablon aşırı yüklemeleri ve boyutu parametreleri el ile eklemek için seçerseniz, iki kez veya üç kat daha fazla zaman büyük olasılıkla kalırsınız.  
  
##  <a name="deprecated_forscope"></a>13. adım. /ZC:forScope-kullanım dışıdır  
 Visual C++ 6.0 bu yana derleyici döngü kapsamını döngü içinde bildirilen değişkenlerin kapsamını sınırlar geçerli standardına uygundur. Derleyici seçeneği [/ZC: forscope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) (**döngü kapsamında uyumluluğu zorla** Proje Özellikleri'nde) olsun veya olmasın bu hata olarak bildirilen denetler. Biz uyumlu olması için kodumuza güncelleştirin ve hemen döngü dışında bildirimi ekleyin. Kod değişiklikleri yapmaktan kaçınmak için bu ayarı C++ proje özelliklerini dil bölümünde değiştirebilirsiniz **yok (/Zc:forScope-)**. Ancak, aklınızda **/Zc:forScope-** Visual C++'ın kodunuzu standart uyacak şekilde değiştirmeniz gerekir, böylece sonunda gelecek bir sürümde kaldırılmış olabilir.  
  
 Bu sorunları düzeltmek görece kolaydır, ancak kodunuzu bağlı olarak kod çok etkileyebilir. Tipik bir sorun olduğunu.  
  
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
  
 Bu durum, derleyici artık C++ Standart uyumlu koduna izin derleyici seçeneği kullanım dışı kaynaklanır. Döngü dışında bir döngü sayacı kullanmanın en yaygın uygulama sayaç bildirimi aşağıdaki düzeltilmiş kod olduğu gibi döngünün dışında da taşınmasını gerektirir şekilde standart, döngü içinde değişken bildirme kapsamı yalnızca, döngü için sınırlar :  
  
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
 Spy ++ son derleyici özgün Visual C++ 6.0 kod taşıma süresi bir hafta hakkında seyri üzerinden kodlama yaklaşık 20 saat sürdü. Sekiz sürümlerden ürünün Visual Studio 6.0 Visual Studio 2015 için aracılığıyla doğrudan yükseltilmiştir. Şimdi tüm yükseltmeler için önerilen yaklaşım büyük ve küçük projelerde budur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Taşıma ve yükseltme: örnekler ve örnek olay incelemeleri](../porting/porting-and-upgrading-examples-and-case-studies.md)   
 [Önceki örnek olay incelemesi: COM Spy](../porting/porting-guide-com-spy.md)