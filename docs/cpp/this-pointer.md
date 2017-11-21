---
title: "Bu işaretçinin | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: this_cpp
dev_langs: C++
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4e77139cdf93d385b92eb87483c1b03541b18650
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="this-pointer"></a>this İşaretçisi
**Bu** işaretçidir yalnızca statik olmayan üye işlevleri içinde erişilebilir bir işaretçi bir **sınıfı**, `struct`, veya **UNION** türü. Üye işlevinin çağrıldığı nesneye işaret eder. Statik üye işlevleri sahip bir **bu** işaretçi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      this   
this->member-identifier  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir nesnenin **bu** işaretçi nesnenin kendisini; parçası değil sonucu yansıtılmaz bir `sizeof` deyimi nesne üzerinde. Bunun yerine, bir nesne için statik olmayan bir üye işlevi çağrıldığında, derleyici tarafından nesnenin adresi gizli bir bağımsız değişken olarak işleve geçirilir. Örneğin, aşağıdaki işlev çağrısı:  
  
```  
myDate.setMonth( 3 );  
```  
  
 şu şekilde yorumlanabilir:  
  
```  
setMonth( &myDate, 3 );  
```  
  
 Nesnenin adresi üye fonksiyonu içinde kullanılabilir **bu** işaretçi. Çoğu kullanımlarını **bu** örtük şunlardır. Gereksiz olsa, açıkça kullanmak yasal, olduğu **bu** sınıf üyeleri için söz konusu olduğunda. Örneğin:  
  
```  
void Date::setMonth( int mn )  
{  
   month = mn;            // These three statements  
   this->month = mn;      // are equivalent  
   (*this).month = mn;  
}  
```  
  
 `*this` ifadesi bir üye işlevinden geçerli nesneyi döndürmek için yaygın olarak kullanılır:  
  
```  
return *this;  
```  
  
 **Bu** işaretçi kendi kendine başvuru karşı koruma sağlamak için de kullanılır:  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  Çünkü **bu** işaretçidir değiştirilemez, atamalar **bu** izin verilmez. C++ önceki uygulamalarında izin atamalarını **bu**.  
  
 Bazen, **bu** işaretçi doğrudan kullanılan — Örneğin, kendi kendine başvuran verileri işlemek için yapıları, geçerli nesne adresini gerekli olduğu.  
  
## <a name="example"></a>Örnek  
  
```  
// this_pointer.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
class Buf   
{  
public:  
    Buf( char* szBuffer, size_t sizeOfBuffer );  
    Buf& operator=( const Buf & );  
    void Display() { cout << buffer << endl; }  
  
private:  
    char*   buffer;  
    size_t  sizeOfBuffer;  
};  
  
Buf::Buf( char* szBuffer, size_t sizeOfBuffer )  
{  
    sizeOfBuffer++; // account for a NULL terminator  
  
    buffer = new char[ sizeOfBuffer ];  
    if (buffer)  
    {  
        strcpy_s( buffer, sizeOfBuffer, szBuffer );  
        sizeOfBuffer = sizeOfBuffer;  
    }  
}  
  
Buf& Buf::operator=( const Buf &otherbuf )   
{  
    if( &otherbuf != this )   
    {  
        if (buffer)  
            delete [] buffer;  
  
        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;   
        buffer = new char[sizeOfBuffer];  
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );  
    }  
    return *this;  
}  
  
int main()  
{  
    Buf myBuf( "my buffer", 10 );  
    Buf yourBuf( "your buffer", 12 );  
  
    // Display 'my buffer'  
    myBuf.Display();  
  
    // assignment opperator  
    myBuf = yourBuf;  
  
    // Display 'your buffer'  
    myBuf.Display();  
}  
```  
  
```Output  
my buffer  
your buffer  
```  
  
## <a name="type-of-the-this-pointer"></a>Bu tür işaretçi  
 **Bu** işaretçinin türü tarafından işlevi bildiriminde değiştirilebilir **const** ve `volatile` anahtar sözcükler. Bir işlevi bu anahtar sözcüklerden birinin veya daha fazlasının özniteliklerini alacak şekilde bildirmek için anahtar sözcükleri işlev bağımsız değişken listesinden sonra ekleyin.  
  
 Bu örneği göz önünde bulundurun:  
  
```  
// type_of_this_pointer1.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Üye işlevi, önceki kod bildirir `X`, burada **bu** işaretçi olarak değerlendirilir bir **const** işaretçi bir **const** nesnesi. Birleşimlerini *MS mod listesi* seçenekleri kullanılabilir ancak bunlar her zaman gösterdiği nesne değiştirme **bu**değil **bu** işaretçi kendisi. Bu nedenle, aşağıdaki bildirimi işlev bildirir `X`; **bu** işaretçi bir **const** işaretçi bir **const** nesnesi:  
  
```  
// type_of_this_pointer2.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Türü **bu** bir üye işlevi aşağıdaki sözdizimi tarafından açıklanan nerede *MS niteleyici listesinde* olabilir ve üye işlevleri bildirimcisi belirlenir **const**veya **volatile** (veya her ikisi de) ve *sınıf türü* sınıfı adıdır:  
  
 *sınıf türü [MS-niteleyici-list]*  **\* const bu**   
  
 Diğer bir deyişle, **bu** her zaman bir const; işaretçidir onu atanamaz.  **Const** veya `volatile` gösterdiği sınıf örneği için üye işlevi bildiriminde kullanılan niteleyicileri Uygula **bu** bu işlev kapsamında.  
  
 Aşağıdaki tabloda, bu değiştiricilerin nasıl çalıştığı hakkında daha fazla bilgi verilmektedir.  
  
### <a name="semantics-of-this-modifiers"></a>Değiştiricilerin Semantiği  
  
|Değiştirici|Açıklama|  
|--------------|-------------|  
|**const**|Üye verileri değiştiremezsiniz. olmayan üye işlevleri çağıramaz **const**.|  
|`volatile`|Üye verileri her erişildiğinde bellekten yüklenir; bazı iyileştirmeler devre dışı bırakılır.|  
  
 Geçirmek için bir hata olduğunu bir **const** değil bir üye işlevi nesnesine **const**. Benzer şekilde, bir `volatile` nesnesini `volatile` olmayan bir üye işlevine geçirmek bir hatadır.  
  
 Üye işlevleri bildirilen **const** üye verileri değiştiremezsiniz — bu tür işlevler içinde **bu** işaretçidir gösteren bir işaretçi bir **const** nesnesi.  
  
> [!NOTE]
>  Olarak Kurucular ve Yıkıcılar bildirilemez **const** veya `volatile`. Ancak, olabilirler üzerinde çağrılan **const** veya `volatile` nesneleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 