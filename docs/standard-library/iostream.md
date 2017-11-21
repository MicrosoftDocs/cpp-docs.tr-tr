---
title: '&lt;iostream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 09/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <iostream>
- iostream/std::cerr
- iostream/std::cin
- iostream/std::clog
- iostream/std::cout
- iostream/std::wcerr
- iostream/std::wcin
- iostream/std::wclog
- iostream/std::wcout
dev_langs: C++
helpviewer_keywords: iostream header
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e5b749f16b2aa66aba486bd4dd3449f4e485683a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltiostreamgt"></a>&lt;iostream&gt;
Okuma ve standart akışlara yazma kontrol nesneleri bildirir. Bu genellikle, giriş ve çıkış bir C++ programı gerçekleştirmek için eklemeniz gerekir yalnızca başlığıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <iostream>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Nesneleri iki gruba ayrılır:  
  
- [cin](#cin), [cout](#cout), [cerr](#cerr), ve [clog](#clog) olan yönelik, bayt geleneksel zamanda tek bayt aktarımları gerçekleştirme.  
  
- [wcin](#wcin), [wcout](#wcout), [wcerr](#wcerr), ve [wclog](#wclog) program dahili olarak işleyen geniş karakterler gelen ve giden çevirme geniş, yerleştirilir.  
  
 Standart giriş gibi bir akış üzerinde belirli işlemleri yaptığınızda, aynı akışta farklı bir yön işlemlerini gerçekleştiremezsiniz. Bu nedenle, bir program birbirinin yerine hem çalışamaz [cin](#cin) ve [wcin](#wcin), örneğin.  
  
 Tüm nesneleri bu başlığı paylaşımın özgü bir özellik bildirilmedi — bunlar oluşturulur tanımladığınız içeren bir çeviri biriminde statik nesneleri önce kabul edilebilir \<iostream >. Eşit şekilde, bu nesnelerin tanımladığınız tür statik nesneler için Yıkıcılar önce yok edilmez varsayabilirsiniz. (Çıkış akışları ancak, program sonlandırma sırasında atılmış olan.) Bu nedenle, güvenli bir şekilde okuyabilir ve program başlatma öncesinde ve sonrasında program sonlandırma standart akışlara yazma.  
  
 Bu garantisi ancak Evrensel, değildir. Statik oluşturucu işlevi başka bir çeviri biriminde çağırabilir. Çağrılan işlev, bu başlığında bildirilen nesneler, hangi çeviri birimleri statik yapısında katılmak belirsiz sipariş verilen yapılandırılmış olduğunu varsayar olamaz. Bu nesneler bu tür bir bağlamda kullanmak için önce sınıfın bir nesnesi oluşturmalıdır [ios_base::Init](../standard-library/ios-base-class.md#init).  
  
### <a name="global-stream-objects"></a>Genel akışı nesneleri  
  
|||  
|-|-|  
|[cerr](#cerr)|Belirtir `cerr` genel akış.|  
|[cin](#cin)|Belirtir `cin` genel akış.|  
|[clog](#clog)|Belirtir `clog` genel akış.|  
|[cout](#cout)|Belirtir `cout` genel akış.|  
|[wcerr](#wcerr)|Belirtir `wcerr` genel akış.|  
|[wcin](#wcin)|Belirtir `wcin` genel akış.|  
|[wclog](#wclog)|Belirtir `wclog` genel akış.|  
|[wcout](#wcout)|Belirtir `wcout` genel akış.|  
  
###  <a name="cerr"></a>cerr  
 Nesne `cerr` nesnesiyle ilişkili bir Akış Arabellek çıktısına denetimleri `stderr`bildirilen \<cstdio >.  
  
```  
extern ostream cerr;  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 Bir [ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Nesne için standart hata çıktısı arabellekten çıkarılan eklemeleri bayt akış olarak denetler. Nesnesi oluşturulduktan sonra ifade `cerr.` [bayrakları](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) sıfır olmayan, olduğundan ve `cerr.tie() == &cout`.  
  
#### <a name="example"></a>Örnek  
  
```cpp  
// iostream_cerr.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
using namespace std;  
  
void TestWide( )   
{  
   int i = 0;  
   wcout << L"Enter a number: ";  
   wcin >> i;  
   wcerr << L"test for wcerr" << endl;  
   wclog << L"test for wclog" << endl;     
}  
  
int main( )   
{  
   int i = 0;  
   cout << "Enter a number: ";  
   cin >> i;  
   cerr << "test for cerr" << endl;  
   clog << "test for clog" << endl;  
   TestWide( );  
}  
```  
  
###  <a name="cin"></a>cin  
 Belirtir `cin` genel akış.  
  
```  
extern istream cin;  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 Bir [IStream](../standard-library/istream-typedefs.md#istream) nesnesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Nesne ayıklamaları standart girdisinden bayt akış olarak denetler. Nesnesi oluşturulduktan sonra arama `cin.` [tie](../standard-library/basic-ios-class.md#tie) döndürür `&` [cout](#cout).  
  
#### <a name="example"></a>Örnek  
  Bu örnekte, `cin` sayısal olmayan karakterler karşılaştığında akışta bit başarısız ayarlar. Program başarısız bit temizler ve devam etmek için akıştan geçersiz karakteri kaldırır.  
  
```  
// iostream_cin.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main()  
{  
   int x;  
   cout << "enter choice:";  
   cin >> x;  
   while (x < 1 || x > 4)  
   {  
      cout << "Invalid choice, try again:";  
      cin >> x;  
      // not a numeric character, probably  
      // clear the failure and pull off the non-numeric character  
      if (cin.fail())  
      {  
         cin.clear();  
         char c;  
         cin >> c;  
      }  
   }  
}  
```  
  
```Output  
  
2  
  
```  
  
###  <a name="clog"></a>clog  
 Belirtir `clog` genel akış.  
  
```  
extern ostream clog;  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 Bir [ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Nesne denetimlerinin eklemeleri standart hata çıktısı için bir bayt akışı arabelleğe.  
  
#### <a name="example"></a>Örnek  
  Bkz: [cerr](#cerr) kullanma örneği için `clog`.  
  
###  <a name="cout"></a>cout  
 Belirtir `cout` genel akış.  
  
```  
extern ostream cout;  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 Bir [ostream](../standard-library/ostream-typedefs.md#ostream) nesnesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Nesne eklemeler standart çıktıya bayt akış olarak denetler.  
  
#### <a name="example"></a>Örnek  
  Bkz: [cerr](#cerr) kullanma örneği için `cout`.  
  
###  <a name="wcerr"></a>wcerr  
 Belirtir `wcerr` genel akış.  
  
```  
extern wostream wcerr;  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 A [wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Nesne için standart hata çıktısı arabellekten çıkarılan eklemeleri geniş bir akış olarak denetler. Nesnesi oluşturulduktan sonra ifade `wcerr.` [bayrakları](../standard-library/ios-base-class.md#flags) `&` [unitbuf](../standard-library/ios-functions.md#unitbuf) sıfır olmayan bir değer değil.  
  
#### <a name="example"></a>Örnek  
  Bkz: [cerr](#cerr) kullanma örneği için `wcerr`.  
  
###  <a name="wcin"></a>wcin  
 Belirtir `wcin` genel akış.  
  
```  
extern wistream wcin;  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 A [wistream](../standard-library/istream-typedefs.md#wistream) nesnesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Nesne ayıklamaları standart girdisinden geniş bir akış olarak denetler. Nesnesi oluşturulduktan sonra arama `wcin.` [tie](../standard-library/basic-ios-class.md#tie) döndürür `&` [wcout](#wcout).  
  
#### <a name="example"></a>Örnek  
  Bkz: [cerr](#cerr) kullanma örneği için `wcin`.  
  
###  <a name="wclog"></a>wclog  
 Belirtir `wclog` genel akış.  
  
```  
extern wostream wclog;  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 A [wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Nesne denetimlerinin standart hata çıktısı eklemelerin geniş bir akış olarak arabelleğe alındı.  
  
#### <a name="example"></a>Örnek  
  Bkz: [cerr](#cerr) kullanma örneği için `wclog`.  
  
###  <a name="wcout"></a>wcout  
 Belirtir `wcout` genel akış.  
  
```  
extern wostream wcout;  
```  
  
#### <a name="return-value"></a>Dönüş Değeri  
 A [wostream](../standard-library/ostream-typedefs.md#wostream) nesnesi.  
  
#### <a name="remarks"></a>Açıklamalar  
 Nesne eklemeler standart çıktıya geniş bir akış olarak denetler.  
  
#### <a name="example"></a>Örnek  
  Bkz: [cerr](#cerr) kullanma örneği için `wcout`.  
  
 `CString`içinde örnekler bir `wcout` deyimi cast, için `const wchar_t*`, aşağıdaki örnekte gösterildiği gibi.  
  
```  
 
    CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;  
```  
  
 Daha fazla bilgi için bkz: [temel CString işlemleri](../atl-mfc-shared/basic-cstring-operations.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream programlama](../standard-library/iostream-programming.md)   
 [iostreams kuralları](../standard-library/iostreams-conventions.md)

