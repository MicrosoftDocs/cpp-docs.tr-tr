---
title: 'Nasıl yapılır: Sıralama Kitaplığını Genişletme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
ms.openlocfilehash: 2a3dccd33b7ad2caee64e31e0f79180dda4649be
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216394"
---
# <a name="how-to-extend-the-marshaling-library"></a>Nasıl yapılır: Sıralama Kitaplığını Genişletme

Bu konuda, veri türleri arasında daha fazla dönüştürme sağlamak için sıralama kitaplığının nasıl genişletileceği açıklanmaktadır. Kullanıcılar, kitaplık tarafından şu anda desteklenmeyen veri dönüştürmelerinden oluşan sıralama kitaplığını genişletebilirler.

Sıralama kitaplığını, bir [Marshal_context sınıfı](../dotnet/marshal-context-class.md)ile veya olmadan iki şekilde genişletebilirsiniz. Yeni dönüştürmenin bir bağlam gerektirip gerektirmediğini anlamak için [C++ ' ta sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md) konusunu gözden geçirin.

Her iki durumda da, ilk olarak yeni sıralama dönüştürmeleri için bir dosya oluşturursunuz. Standart sıralama kitaplığı dosyalarının bütünlüğünü korumak için bunu yapabilirsiniz. Bir proje için başka bir bilgisayara veya başka bir programcıya bağlantı noktası eklemek istiyorsanız, yeni sıralama dosyasını, projenin geri kalanıyla birlikte kopyalamanız gerekir. Bu şekilde, projeyi alan Kullanıcı yeni dönüştürmeleri alacak şekilde garanti edilir ve herhangi bir kitaplık dosyasını değiştirmek zorunda olmayacaktır.

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>Sıralama kitaplığını bağlam gerektirmeyen bir dönüşümle genişletmek için

1. Yeni sıralama işlevlerini depolamak için bir dosya oluşturun, örneğin, MyMarshal. h.

1. Bir veya daha fazla sıralama kitaplığı dosyası ekleyin:

   - temel türler için Marshal. h.

   - Windows veri türleri için marshal_windows. h.

   - C++ standart kitaplığı veri türleri için marshal_cppstd. h.

   - ATL veri türleri için marshal_atl. h.

1. Dönüştürme işlevini yazmak için bu adımların sonundaki kodu kullanın. Bu kodda, ' ye dönüştürülecek tür, ÖĞESINDEN dönüştürülecek türdür ve `from` dönüştürülecek parametredir.

1. Parametreyi bir nesnesine dönüştürmek için, dönüştürme mantığı ile ilgili açıklamayı kodla değiştirin `from` ve dönüştürülen nesneyi döndürün.

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

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>Sıralama kitaplığını bağlam gerektiren bir dönüşümle genişletmek için

1. Yeni sıralama işlevlerini depolamak için bir dosya oluşturun; örneğin, MyMarshal. h

1. Bir veya daha fazla sıralama kitaplığı dosyası ekleyin:

   - temel türler için Marshal. h.

   - Windows veri türleri için marshal_windows. h.

   - C++ standart kitaplığı veri türleri için marshal_cppstd. h.

   - ATL veri türleri için marshal_atl. h.

1. Dönüştürme işlevini yazmak için bu adımların sonundaki kodu kullanın. Bu kodda, ' ye dönüştürülecek tür, ' den dönüştürülecek türdür, `toObject` sonucun depolanacak bir işaretçidir ve `fromObject` dönüştürülecek parametredir.

1. Öğesini uygun boş değere başlatmak için kodla başlatma hakkındaki açıklamayı değiştirin `toPtr` . Örneğin, bir işaretçisiyse, olarak ayarlayın `NULL` .

1. Parametreyi türüne dönüştürmek için dönüştürme mantığı ile ilgili yorumu değiştirin `from` . *TO* Dönüştürülen bu nesne içinde depolanacak `toPtr` .

1. `toObject`Dönüştürülmüş nesneniz olarak ayarlanacak kodla ilgili açıklamayı değiştirin `toObject` .

1. Tarafından ayrılan tüm belleği boşaltmak için yerel kaynakları kodla Temizleme hakkındaki açıklamayı değiştirin `toPtr` . `toPtr`Kullanılarak ayrılan bellek **`new`** , **`delete`** belleği serbest bırakmak için kullanın.

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

Aşağıdaki örnek, sıralama kitaplığını bağlam gerektirmeyen bir dönüştürme ile genişletir. Bu örnekte, kod, çalışan bilgilerini yerel bir veri türünden yönetilen bir veri türüne dönüştürür.

```cpp
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

Önceki örnekte, `marshal_as` işlevi dönüştürülen verilere bir tanıtıcı döndürür. Bu, verilerin ek bir kopyasının oluşturulmasını engellemek için yapılır. Değişkenin doğrudan döndürülmesi, bununla ilişkili gereksiz bir performans maliyetine sahip olur.

```Output
Managed name: Jeff Smith
Managed address: 123 Main Street
Managed zip code: 98111
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, çalışan bilgilerini yönetilen bir veri türünden yerel bir veri türüne dönüştürür. Bu dönüştürme bir sıralama bağlamı gerektirir.

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[C++ ' da sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md)
