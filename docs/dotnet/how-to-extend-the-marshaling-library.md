---
title: 'Nasıl yapılır: Hazırlama kitaplığını genişletme'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
ms.openlocfilehash: f289539807b1e9499cef51427d3f6a494545cc60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387311"
---
# <a name="how-to-extend-the-marshaling-library"></a>Nasıl yapılır: Hazırlama kitaplığını genişletme

Bu konuda, veri türleri arasında daha fazla dönüştürme sağlamak için hazırlama kitaplığını genişletme açıklanmaktadır. Kullanıcılar şu anda kitaplığı tarafından desteklenen herhangi bir veri dönüştürmesi için sıralama kitaplığı genişletebilirsiniz.

Sıralama kitaplığı - içeren veya içermeyen iki yoldan biriyle genişletebileceğiniz bir [; marshal_context Class](../dotnet/marshal-context-class.md). Gözden geçirme [Overview of Marshaling c++](../dotnet/overview-of-marshaling-in-cpp.md) yeni dönüştürme bir bağlamı gerekli olup olmadığını belirlemek için.

Her iki durumda da, ilk yeni sıralama dönüştürmeleri için bir dosya oluşturun. Standart kitaplık dosyalarını hazırlama bütünlüğünü korumak için bunu. Bir proje başka bir bilgisayara veya başka bir programcı bağlantı istiyorsanız, projenin geri kalanıyla birlikte yeni hazırlama dosyasını kopyalamanız gerekir. Bu şekilde proje engellenmesiyle kullanıcının yeni dönüştürmeleri almak için garantili ve tüm kitaplık dosyaları değiştirmek zorunda değildir.

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>Bir bağlam gerektirmeyen bir dönüştürme ile hazırlama kitaplığını genişletme

1. Yeni sıralama İşlevler, örneğin, MyMarshal.h depolamak için bir dosya oluşturun.

1. Bir veya daha fazla sıralama kitaplığı dosyaları şunları içerir:

   - Taban türleri için Marshal.h.

   - windows veri türleri için marshal_windows.h.

   - için marshal_cppstd.h C++ standart kitaplık türleri.

   - ATL veri türleri için marshal_atl.h.

1. Kod, dönüştürme işlevi yazmak için bu adımları sonunda kullanın. Bu kod için dönüştürmek için türdür, FROM, dönüştürmek için türü ve `from` dönüştürülecek parametredir.

1. Dönüştürme mantığı hakkında açıklama dönüştürmek için kod ile değiştirin `from` parametresi için bir nesnenin içine yazın ve dönüştürülen nesne döndürür.

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

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>Bir bağlam gerektiren bir dönüştürme hazırlama kitaplığını genişletme

1. Yeni sıralama İşlevler, örneğin, MyMarshal.h depolamak için bir dosya oluşturun

1. Bir veya daha fazla sıralama kitaplığı dosyaları şunları içerir:

   - Taban türleri için Marshal.h.

   - windows veri türleri için marshal_windows.h.

   - için marshal_cppstd.h C++ standart kitaplık türleri.

   - ATL veri türleri için marshal_atl.h.

1. Kod, dönüştürme işlevi yazmak için bu adımları sonunda kullanın. Bu kod için dönüştürmek için türdür, FROM, dönüştürmek için türü `toObject` sonucun depolanacağı bir işaretçidir ve `fromObject` dönüştürülecek parametredir.

1. Başlatma başlatmak için kod ile ilgili açıklamayı değiştirme `toPtr` uygun boş değere. Bir işaretçi ise, örneğin, ayarlayın `NULL`.

1. Dönüştürme mantığı hakkında açıklama dönüştürmek için kod ile değiştirin `from` parametresine bir nesne *Kime* türü. Dönüştürülen bu nesne içinde depolanan `toPtr`.

1. Ayarlamayla ilgili açıklamayı değiştirme `toObject` ayarlamak üzere kod ile `toObject` , dönüştürülen nesne.

1. Tarafından ayrılan belleği serbest bırakacak koda sahip yerel kaynakları temizleme hakkında yorum değiştirin `toPtr`. Varsa `toPtr` kullanarak ayrılan bellek `new`, kullanın `delete` belleği boşaltmak için.

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

Aşağıdaki örnekte, bir bağlam gerektirmeyen bir dönüştürme ile sıralama kitaplığı genişletir. Bu örnekte, kod çalışanların bilgilerinin yerel veri türünden bir yönetilen veri türüne dönüştürür.

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

Önceki örnekte, `marshal_as` işlevi veriye bir tanıtıcı döndürür. Bu, verileri başka bir kopyası oluşturuluyor engellemek için yapıldı. Değişken doğrudan döndüren bir gereksiz performans maliyeti ilişkili.

```Output
Managed name: Jeff Smith
Managed address: 123 Main Street
Managed zip code: 98111
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, çalışanların bilgilerinin yönetilen veri türünden bir yerel veri türüne dönüştürür. Bu dönüştürme hazırlama bağlamı gerektirir.

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

## <a name="see-also"></a>Ayrıca bkz.

[Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)
