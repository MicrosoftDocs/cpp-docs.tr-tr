---
title: "Nasıl yapılır: hazırlama kitaplığını genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ee919e1faa37959d25e8e42581c8cde80d640337
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-extend-the-marshaling-library"></a>Nasıl yapılır: Hazırlama Kitaplığını Genişletme
Bu konuda, veri türleri arasında daha fazla dönüştürme sağlamak için hazırlama kitaplığını genişletme açıklanmaktadır. Kullanıcılar şu anda kitaplığı tarafından desteklenen herhangi bir veri dönüştürmesi için hazırlama kitaplığını genişletme.  
  
 Hazırlama kitaplığını - olan veya olmayan iki yoldan biriyle genişletebilirsiniz bir [marshal_context sınıfı](../dotnet/marshal-context-class.md). Gözden geçirme [, genel bakış hazırlama c++](../dotnet/overview-of-marshaling-in-cpp.md) yeni bir dönüştürme bir bağlam gerekip gerekmediğini belirlemek için konu.  
  
 Her iki durumda da ilk yeni hazırlama dönüştürmesi için bir dosya oluşturun. Standart kitaplık dosyalarını hazırlama bütünlüğünü korumak için bunu. Bağlantı noktası başka bir bilgisayara veya başka bir programcı proje istiyorsanız, projeyi geri kalanı ile birlikte yeni hazırlama dosyasını kopyalamanız gerekir. Bu şekilde projeyi alan kullanıcının yeni dönüştürmeleri alacağı garanti ve herhangi bir kitaplık dosyasını değiştirmek zorunda kalmazsınız.  
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>Bir bağlam gerektirmeyen bir dönüştürme ile hazırlama kitaplığını genişletme  
  
1.  Yeni hazırlama işlevlerini, örneğin, MyMarshal.h depolamak için bir dosya oluşturun.  
  
2.  Bir veya daha fazla sıralama kitaplık dosyaları şunları içerir:  
  
    -   Taban türleri için Marshal.h.  
  
    -   marshal_windows.h windows veri türleri için.  
  
    -   C++ Standart Kitaplığı veri türleri için marshal_cppstd.h.  
  
    -   ATL veri türleri için marshal_atl.h.  
  
3.  Kod adımları sonunda dönüştürme işlevi yazmak için kullanın. Bu kodda, TO dönüştürmek için türdür, FROM dönüştürülecek türdür ve `from` dönüştürülecek parametredir.  
  
4.  Dönüştürme mantığı hakkındaki açıklamayı dönüştürmek için kod ile değiştirin `from` parametresi için bir nesne içine yazın ve dönüştürülen nesne döndürür.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      inline TO marshal_as<TO, FROM> (const FROM& from) {  
         // Insert conversion logic here, and return a TO parameter.  
      }  
   }  
}  
```  
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>Bağlam gerektiren bir dönüştürme ile hazırlama kitaplığını genişletme  
  
1.  Yeni hazırlama işlevlerini, örneğin, MyMarshal.h depolamak için bir dosya oluşturun  
  
2.  Bir veya daha fazla sıralama kitaplık dosyaları şunları içerir:  
  
    -   Taban türleri için Marshal.h.  
  
    -   marshal_windows.h windows veri türleri için.  
  
    -   C++ Standart Kitaplığı veri türleri için marshal_cppstd.h.  
  
    -   ATL veri türleri için marshal_atl.h.  
  
3.  Kod adımları sonunda dönüştürme işlevi yazmak için kullanın. Bu kod için dönüştürmek için türdür, FROM dönüştürülecek türü `toObject` gösteren bir işaretçidir sonuç depolanacağı ve `fromObject` dönüştürülecek parametredir.  
  
4.  Başlatmak için kod ile başlatma hakkında açıklamayı değiştirin `toPtr` uygun boş değere. Bir işaretçi ise, örneğin, ayarlayın `NULL`.  
  
5.  Dönüştürme mantığı hakkındaki açıklamayı dönüştürmek için kod ile değiştirin `from` bir nesnenin parametresine *Kime* türü. Dönüştürülen bu nesne içinde depolanan `toPtr`.  
  
6.  Ayar hakkındaki açıklamayı değiştirin `toObject` ayarlamak için kod ile `toObject` dönüştürülen nesnenize.  
  
7.  Yerel kaynaklar tarafından ayrılan belleği boşaltmak için kod ile temizleme hakkında açıklamayı değiştirin `toPtr`. Varsa `toPtr` kullanarak bellek tahsis `new`, kullanın `delete` belleği boşaltmak için.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<TO, FROM> : public context_node_base  
      {  
      private:  
         TO toPtr;  
      public:  
         context_node(TO& toObject, FROM fromObject)  
         {  
            // (Step 4) Initialize toPtr to the appropriate empty value.  
            // (Step 5) Insert conversion logic here.  
            // (Step 6) Set toObject to the converted parameter.  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // (Step 7) Clean up native resources.  
         }  
      };  
   }  
}   
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir bağlam gerektirmeyen bir dönüştürme ile hazırlama kitaplığını genişletir. Bu örnekte, kod çalışan bilgisini yerel veri türünden bir yönetilen veri türüne dönüştürür.  
  
```  
// MyMarshalNoContext.cpp  
// compile with: /clr  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   char* name;  
   char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {  
         ManagedEmp^ toValue = gcnew ManagedEmp;  
         toValue->name = marshal_as<System::String^>(from.name);  
         toValue->address = marshal_as<System::String^>(from.address);  
         toValue->zipCode = from.zipCode;  
         return toValue;  
      }  
   }  
}  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {   
   NativeEmp employee;  
  
   employee.name = "Jeff Smith";  
   employee.address = "123 Main Street";  
   employee.zipCode = 98111;  
  
   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);  
  
   Console::WriteLine("Managed name: {0}", result->name);  
   Console::WriteLine("Managed address: {0}", result->address);  
   Console::WriteLine("Managed zip code: {0}", result->zipCode);  
  
   return 0;  
}  
```  
  
 Önceki örnekte, `marshal_as` işlevi bir tanıtıcı veriye döndürür. Bu verileri başka bir kopyası oluşturuluyor önlemek için gerçekleştirilir. Değişkeni doğrudan döndürme gereksiz performans maliyeti kendisiyle ilişkilendirilmiş.  
  
```Output  
Managed name: Jeff Smith  
Managed address: 123 Main Street  
Managed zip code: 98111  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek çalışan bilgisini yönetilen veri türünden bir yerel veri türüne dönüştürür. Bu dönüştürme hazırlama bağlamı gerektirir.  
  
```  
// MyMarshalContext.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   const char* name;  
   const char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base  
      {  
      private:  
         NativeEmp* toPtr;  
         marshal_context context;  
      public:  
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)  
         {  
            // Conversion logic starts here  
            toPtr = NULL;  
  
            const char* nativeName;  
            const char* nativeAddress;  
  
            // Convert the name from String^ to const char*.  
            System::String^ tempValue = fromObject->name;  
            nativeName = context.marshal_as<const char*>(tempValue);  
  
            // Convert the address from String^ to const char*.  
            tempValue = fromObject->address;  
            nativeAddress = context.marshal_as<const char*>(tempValue);  
  
            toPtr = new NativeEmp();  
            toPtr->name = nativeName;  
            toPtr->address = nativeAddress;  
            toPtr->zipCode = fromObject->zipCode;  
  
            toObject = toPtr;  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // When the context is deleted, it will free the memory  
            // allocated for toPtr->name and toPtr->address, so toPtr  
            // is the only memory that needs to be freed.  
            if (toPtr != NULL) {  
               delete toPtr;  
               toPtr = NULL;  
            }  
         }  
      };  
   }  
}   
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   ManagedEmp^ employee = gcnew ManagedEmp();  
  
   employee->name = gcnew String("Jeff Smith");  
   employee->address = gcnew String("123 Main Street");  
   employee->zipCode = 98111;  
  
   marshal_context context;  
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);  
  
   if (result != NULL) {  
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",  
         result->name, result->address, result->zipCode);  
   }  
  
   return 0;  
}  
```  
  
```Output  
Native name: Jeff Smith  
Native address: 123 Main Street  
Native zip code: 98111  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)