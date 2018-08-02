---
title: Bu işaretçinin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- this_cpp
dev_langs:
- C++
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f63b2d129e0eb6e9986942e4286eb1728d4be797
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462225"
---
# <a name="this-pointer"></a>this İşaretçisi
**Bu** işaretçisine, yalnızca statik olmayan üye işlevlerinin içinden erişilebilir bir **sınıfı**, **yapı**, veya **birleşim** türü. Üye işlevinin çağrıldığı nesneye işaret eder. Statik üye işlevleri yoktur bir **bu** işaretçi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
this   
this->member-identifier  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir nesnenin **bu** işaretçisi nesnenin kendisini; bir parçası değil sonucuna yansıtılmaz bir **sizeof** deyimi nesne üzerinde. Bunun yerine, bir nesne için statik olmayan bir üye işlevi çağrıldığında, derleyici tarafından nesnenin adresi gizli bir bağımsız değişken olarak işleve geçirilir. Örneğin, aşağıdaki işlev çağrısı:  
  
```cpp 
myDate.setMonth( 3 );  
```  
  
 şu şekilde yorumlanabilir:  
  
```cpp 
setMonth( &myDate, 3 );  
```  
  
 Nesnenin adresi olarak üye işlev içinden kullanılabilir **bu** işaretçi. Çoğu kullanım **bu** örtüktür. Gereksiz olsa da, açıkça kullanılacak hukuk olduğu **bu** sınıf üyelerine başvuru yaparken. Örneğin:  
  
```cpp 
void Date::setMonth( int mn )  
{  
   month = mn;            // These three statements  
   this->month = mn;      // are equivalent  
   (*this).month = mn;  
}  
```  
  
 `*this` ifadesi bir üye işlevinden geçerli nesneyi döndürmek için yaygın olarak kullanılır:  
  
```cpp 
return *this;  
```  
  
 **Bu** işaretçi kendi kendine başvuru yapmaya karşı koruma sağlamak için de kullanılır:  
  
```cpp 
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  Çünkü **bu** this işaretçisi atamaları **bu** izin verilmez. C++'ın önceki uygulamaları atama yapmaya izin **bu**.  
  
 Bazen, **bu** işaretçisi doğrudan kullanılır — Örneğin, kendine başvuru yapan veri yapılarını işlemek için geçerli nesnenin adresinin gerekli olduğu.  
  
## <a name="example"></a>Örnek  
  
```cpp 
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
  
## <a name="type-of-the-this-pointer"></a>Bu öğenin türü işaretçi  
 **Bu** işaretçinin türü, işlev bildiriminde tarafından değiştirilebilir **const** ve **geçici** anahtar sözcükleri. Bir işlevi bu anahtar sözcüklerden birinin veya daha fazlasının özniteliklerini alacak şekilde bildirmek için anahtar sözcükleri işlev bağımsız değişken listesinden sonra ekleyin.  
  
 Bu örneği göz önünde bulundurun:  
  
```cpp 
// type_of_this_pointer1.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Yukarıdaki kod, bir üye işlev bildirir `X`, hangi **bu** işaretçisi olarak kabul edildiği bir **const** işaretçi bir **const** nesne. Birleşimlerini *cv mod listesi* seçenekleri kullanılabilir ancak bunlar her zaman işaret ettiği nesneyi değiştirmek **bu**değil **bu** işaretçinin kendisinde. Bu nedenle, aşağıdaki bildirimi işlev bildirir `X`; **bu** işaretçi bir **const** işaretçi bir **const** nesnesi:  
  
```cpp 
// type_of_this_pointer2.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Türünü **bu** üye işlevi aşağıdaki sözdizimi tarafından açıklanan burada *cv niteleyici listesi* olabilir ve üye işlevleri bildirimcisinden belirlendiği **const**veya **geçici** (veya her ikisi de) ve *sınıf türü* sınıf adıdır:  
  
 *[cv niteleyici listesi] sınıf türü* **\* const bu**  
  
 Diğer bir deyişle, **bu** her zaman bir const işaretçisidir; olduğundan yeniden atanamaz.  **Const** veya **geçici** işaret ettiği sınıf örneği uygulanacağı üye işlevi bildiriminde kullanılan niteleyicileri **bu** bu işlevin kapsamında.  
  
 Aşağıdaki tabloda, bu değiştiricilerin nasıl çalıştığı hakkında daha fazla bilgi verilmektedir.  
  
### <a name="semantics-of-this-modifiers"></a>Değiştiricilerin Semantiği  
  
|Değiştirici|Açıklama|  
|--------------|-------------|  
|**const**|Üye verilerini değiştiremez; olmayan üye işlevleri çağrılamaz **const**.|  
|**volatile**|Üye verileri her erişildiğinde bellekten yüklenir; bazı iyileştirmeler devre dışı bırakılır.|  
  
 Geçirilecek bir hata olduğunu bir **const** olmayan bir üye işlev nesnesine **const**. Benzer şekilde, bu geçirmek bir hatadır bir **geçici** olmayan bir üye işlev nesnesine **geçici**.  
  
 Olarak bildirilen üye işlevleri **const** üye verilerini değiştiremez; böyle işlevlerde, **bu** işaretçisidir bir işaretçi bir **const** nesne.  
  
> [!NOTE]
>  Olarak oluşturucular ve Yıkıcılar bildirilemez **const** veya **geçici**. Ancak, olabilirler çağrılabilirler **const** veya **geçici** nesneleri.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)   