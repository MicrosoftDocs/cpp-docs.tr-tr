---
title: "İç içe geçmiş sınıf bildirimleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 247be4e212efbe2b8061deed200a8350b87fc7a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="nested-class-declarations"></a>İç İçe Geçmiş Sınıf Bildirimleri
Bir sınıf başka bir sınıf kapsamında bildirilebilir. Bu tür bir sınıf bir "sınıfı iç içe." olarak adlandırılır İç içe geçmiş sınıflar kapsayan sınıfı kapsamında olduğu kabul edilir ve bu kapsam içinde kullanılabilir. İç içe bir sınıf hemen kapsayan kapsamı dışında kapsamdan başvurmak için bir tam ad kullanmanız gerekir.  
  
 Aşağıdaki örnek, iç içe geçmiş sınıflar bildirmeniz gösterilmektedir:  
  
```  
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
  
 `BufferedIO::BufferedInput`ve `BufferedIO::BufferedOutput` içinde bildirilen `BufferedIO`. Bu sınıf adları sınıf kapsamı dışında görünmez `BufferedIO`. Ancak, bir nesne türü `BufferedIO` türdeki tüm nesnelerin içermiyor `BufferedInput` veya `BufferedOutput`.  
  
 İç içe geçmiş sınıflar doğrudan adları, tür adları statik üyeleri ve numaralandırmalar kapsayan sınıfından yalnızca adlarını kullanabilirsiniz. Diğer sınıf üyelerinin adlarını kullanmak için işaretçileri, başvuru veya nesne adlarını kullanmanız gerekir.  
  
 Yukarıdaki içinde `BufferedIO` örnek, numaralandırma `IOError` iç içe geçmiş sınıflardaki üye işlevleri tarafından doğrudan erişilebilir `BufferedIO::BufferedInput` veya `BufferedIO::BufferedOutput`işlevinde gösterildiği gibi `good`.  
  
> [!NOTE]
>  İç içe geçmiş sınıflar, yalnızca sınıf kapsamı içinde türleri bildirin. Değil neden içerdiği nesnelerin oluşturulacak iç içe geçmiş sınıf yaparlar. Önceki örnekte iki iç içe geçmiş sınıflar bildirir ancak bu sınıfın türlerinin herhangi bir nesne bildirmiyor.  
  
 Tür adı ile birlikte ileriye dönük bildirimi bildirirken bir kapsam görünürlük iç içe geçmiş sınıf bildiriminin istisnadır.  Bu durumda, ileriye dönük bildirimi tarafından bildirilen sınıf adı küçük kapsayan sınıf olmayan kapsamı olarak tanımlanan kendi kapsamıyla çevreleyen sınıf dışında görünür olur.  Örneğin:  
  
```  
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
 Üye işlevleri iç içe geçmiş sınıflarda bildirilen dosya kapsamda tanımlanabilir. Önceki örnekte yazılmış:  
  
```  
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
  
 Önceki örnekte *tam-türü-adının* sözdizimi işlev adı bildirmek için kullanılır. Bildirimi:  
  
```  
BufferedIO::BufferedInput::read()  
```  
  
 anlamına gelir " `read` üye fonksiyonu `BufferedInput` kapsamında sınıfı `BufferedIO` sınıfı." Bu bildirim kullandığından *tam-türü-adının* sözdizimi, aşağıdaki biçimde yapıları mümkündür:  
  
```  
typedef BufferedIO::BufferedInput BIO_INPUT;  
  
int BIO_INPUT::read()  
```  
  
 Önceki bildirimi Öncekine eşdeğerdir ancak kullandığı bir `typedef` sınıf adları yerine adı.  
  
## <a name="friend-functions-in-nested-classes"></a>Arkadaş işlevleri iç içe geçmiş sınıflardaki  
 Arkadaş işlevleri iç içe bir sınıf içinde bildirilen kapsayan sınıfı iç içe geçmiş sınıf kapsamında olduğu kabul edilir. Bu nedenle, arkadaş işlevleri üyeleri ya da kapsayan sınıfının üye işlevleri için hiçbir özel erişim ayrıcalıklara sahip. Arkadaş işlevinde iç içe geçmiş sınıf bildirilmiş bir ad kullanmak istiyorsanız ve arkadaş işlevi dosya kapsamda tanımlı nitelenmiş tür adları şu şekilde kullanın:  
  
```  
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
  
 Aşağıdaki kod işlevi gösterir `GetExtendedErrorStatus` arkadaş işlevi bildirildi. Dosya kapsamda tanımlanan işlevinde bir ileti sınıfı üyesi statik diziden kopyalanır. Unutmayın, daha iyi bir uygulama `GetExtendedErrorStatus` olarak bildirmek için:  
  
```  
int GetExtendedErrorStatus( char *message )  
```  
  
 Önceki arabirimiyle birkaç sınıflarını kopyalanan hata iletisi istedikleri bellek konumuna geçirerek bu işlev hizmetlerini kullanabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıflar ve Yapılar](../cpp/classes-and-structs-cpp.md)