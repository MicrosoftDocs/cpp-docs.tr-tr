---
title: İç içe geçmiş sınıf bildirimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], declaring
- declarations, class
- nested classes [C++]
- nested classes [C++], declaring
- declaring classes [C++]
- declarations, nested classes
ms.assetid: c02e471d-b7f9-41b8-8ef6-2323f006dbd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86c61792ab20bc0c10c9297d2a66588dd3c066ef
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948048"
---
# <a name="nested-class-declarations"></a>İç İçe Geçmiş Sınıf Bildirimleri
Bir sınıf başka bir sınıf kapsamında bildirilebilir. Bu tür bir sınıfının bir "sınıfı iç içe geçmiş." olarak adlandırılır İç içe geçmiş sınıflar, kapsayan sınıf kapsamında değerlendirilir ve bu kapsam içinde kullanılabilir. İç içe geçmiş bir sınıf için hemen kapsayan kapsamı dışında bir kapsamdan başvurmak için bir tam adı kullanmanız gerekir.  
  
 Aşağıdaki örnekte, iç içe geçmiş sınıflar bildirmeniz gösterilmektedir:  
  
```cpp 
// nested_class_declarations.cpp  
class BufferedIO  
{  
public:  
   enum IOError { None, Access, General };  
  
   // Declare nested class BufferedInput.  
   class BufferedInput  
   {  
   public:  
      int read();  
      int good()  
      {  
         return _inputerror == None;  
      }  
   private:  
       IOError _inputerror;  
   };  
  
   // Declare nested class BufferedOutput.  
   class BufferedOutput  
   {  
      // Member list  
   };  
};  
  
int main()  
{  
}  
```  
  
 `BufferedIO::BufferedInput` ve `BufferedIO::BufferedOutput` içinde bildirilen `BufferedIO`. Bu sınıf adları sınıf kapsamı dışında görünür değildir `BufferedIO`. Ancak, bir nesne türü `BufferedIO` türlerinin herhangi bir nesne içermiyor `BufferedInput` veya `BufferedOutput`.  
  
 İç içe geçmiş sınıflar doğrudan adları, tür adları, statik üyeleri ve yalnızca kapsayan sınıfından numaralandırıcıların adları kullanabilirsiniz. Diğer sınıf üyelerinin adları kullanmak için işaretçiler, başvurular veya nesne adlarını kullanmanız gerekir.  
  
 Önceki içinde `BufferedIO` örneği, numaralandırma `IOError` doğrudan iç içe geçmiş sınıflardaki üye işlevleri tarafından erişilebilir `BufferedIO::BufferedInput` veya `BufferedIO::BufferedOutput`işlevinde görüldüğü gibi `good`.  
  
> [!NOTE]
>  İç içe geçmiş sınıflar, yalnızca sınıf kapsamı içinde türlerini bildirir. Bunlar, iç içe geçmiş sınıf oluşturulacak neden yer alan nesneleri yapın. Yukarıdaki örnekte, iç içe iki sınıf bildirdiyse ama tüm bu sınıf türü nesneleri bildirmiyor.  
  
 Bir tür adı ile birlikte İleri dönük bildiriminin bildirildiğinde bir kapsam görünürlük iç içe geçmiş sınıf bildiriminin istisnadır.  Bu durumda, İleri dönük bildirimi tarafından bildirilen sınıf adı kapsamı ile en küçük kapsayan sınıf olmayan kapsamı tanımlanmış kapsayan sınıfa dışında görülebilir.  Örneğin:  
  
```cpp 
// nested_class_declarations_2.cpp  
class C  
{  
public:  
    typedef class U u_t; // class U visible outside class C scope  
    typedef class V {} v_t; // class V not visible outside class C  
};  
  
int main()  
{  
    // okay, forward declaration used above so file scope is used  
    U* pu;  
  
    // error, type name only exists in class C scope  
    u_t* pu2; // C2065  
  
    // error, class defined above so class C scope  
    V* pv; // C2065  
  
    // okay, fully qualified name  
    C::V* pv2;  
}  
```  
  
## <a name="access-privilege-in-nested-classes"></a>İç içe geçmiş sınıflardaki erişim ayrıcalığı  
 Bir sınıfı başka bir sınıf içinde iç içe geçirmek, iç içe geçmiş sınıfın üye işlevlerine özel erişim ayrıcalıkları vermez. Benzer şekilde, çevreleyen sınıfın üye işlevlerinin iç içe geçmiş sınıf üyeleri için özel erişimi yoktur.  
  
## <a name="member-functions-in-nested-classes"></a>İç içe geçmiş sınıflardaki üye işlevleri  
 İç içe geçmiş sınıflarda bildirilen üye işlevleri, dosya kapsamı içinde tanımlanabilir. Yukarıdaki örnekte yazılmış:  
  
```cpp 
// member_functions_in_nested_classes.cpp  
class BufferedIO  
{  
public:  
    enum IOError { None, Access, General };  
    class BufferedInput  
    {  
    public:  
        int read(); // Declare but do not define member  
        int good(); //  functions read and good.  
    private:  
        IOError _inputerror;  
    };  
  
    class BufferedOutput  
    {  
        // Member list.  
    };  
};  
// Define member functions read and good in  
//  file scope.  
int BufferedIO::BufferedInput::read()  
{  
   return(1);  
}  
  
int BufferedIO::BufferedInput::good()  
{  
    return _inputerror == None;  
}  
int main()  
{  
}  
```  
  
 Önceki örnekte *nitelikli tür adı* söz dizimi, işlev adını bildirmek için kullanılır. Bildirim:  
  
```cpp 
BufferedIO::BufferedInput::read()  
```  
  
 anlamına gelir " `read` üyesi işlevi `BufferedInput` kapsamında sınıfı `BufferedIO` sınıfı." Bu bildirim kullandığından *nitelikli tür adı* söz dizimi yapıları aşağıdaki biçime mümkündür:  
  
```cpp 
typedef BufferedIO::BufferedInput BIO_INPUT;  
  
int BIO_INPUT::read()  
```  
  
 Yukarıdaki bildirim, Öncekine eşdeğerdir, ancak bunu kullanan bir **typedef** sınıf adları yerine adı.  
  
## <a name="friend-functions-in-nested-classes"></a>Arkadaş işlevleri iç içe geçmiş sınıflardaki  
 İç içe geçmiş bir sınıfta bildirilen arkadaş işlevleri iç içe geçmiş sınıf, kapsayan sınıf kapsamı içinde olarak değerlendirilir. Bu nedenle, arkadaş işlev üyeleri veya kapsayan sınıfın üye işlevleri için hiçbir özel erişim ayrıcalıkları elde edin. İç içe geçmiş bir sınıf bir arkadaş işlev içinde bildirilen bir ad kullanmak istediğiniz ve dosya kapsamında tanımlanan arkadaş işlevi, nitelenmiş tür adlarını şu şekilde kullanın:  
  
```cpp 
// friend_functions_and_nested_classes.cpp  
  
#include <string.h>  
  
enum  
{  
    sizeOfMessage = 255  
};  
  
char *rgszMessage[sizeOfMessage];  
  
class BufferedIO  
{  
public:  
    class BufferedInput  
    {  
    public:  
        friend int GetExtendedErrorStatus();  
        static char *message;  
        static int  messageSize;  
        int iMsgNo;  
   };  
};  
  
char *BufferedIO::BufferedInput::message;  
int BufferedIO::BufferedInput::messageSize;  
  
int GetExtendedErrorStatus()  
{  
    int iMsgNo = 1; // assign arbitrary value as message number  
  
    strcpy_s( BufferedIO::BufferedInput::message,  
              BufferedIO::BufferedInput::messageSize,  
              rgszMessage[iMsgNo] );  
  
    return iMsgNo;  
}  
  
int main()  
{  
}  
```  
  
 Aşağıdaki kod, işlev göstermektedir `GetExtendedErrorStatus` bir arkadaş işlev bildirilir. Dosya kapsamında tanımlanan işlevinde bir ileti sınıfı üyesi bir statik dizisinden kopyalanır. Unutmayın, daha iyi bir uygulama `GetExtendedErrorStatus` olarak bildirmek için:  
  
```cpp 
int GetExtendedErrorStatus( char *message )  
```  
  
 Önceki arabirimiyle birkaç sınıfı bir bellek konumuna kopyalanan hata iletisi istedikleri geçirerek Hizmetleri bu işlevi kullanabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)