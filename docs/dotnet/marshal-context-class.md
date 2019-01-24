---
title: marshal_context Sınıfı
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- msclr::marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 25fc2be80ba0e5d8c7f76cee1f22eed4d1bb4fc7
ms.sourcegitcommit: 9813e146a4eb30929d8352872859e8fcb7ff6d2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54805987"
---
# <a name="marshalcontext-class"></a>marshal_context Sınıfı

Bu sınıf, yerel ve yönetilen ortamlar arasında verileri dönüştürür.

## <a name="syntax"></a>Sözdizimi

```cpp
class marshal_context
```

## <a name="remarks"></a>Açıklamalar

Kullanım `marshal_context` sınıfı için bir bağlam gerektiren veri dönüştürme. Hangi dönüştürmeler bir bağlamda gerektirir ve hangi hazırlama dosyasını dahil olmak zorundadır hakkında daha fazla bilgi için bkz. [C++'da hazırlamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md). Bir bağlam kullandığınızda hazırlama sonucu yalnızca kadar geçerli olan `marshal_context` nesnesi yok edildiğinde. Sonuç korumak için verileri kopyalamanız gerekir.

Aynı `marshal_context` çok sayıda veri dönüştürme için kullanılabilir. Bu şekilde bağlamı yeniden sıralama önceki çağrılarının sonucunu etkilemez.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel oluşturucular

|Ad|Açıklama| 
|---------|-----------| 
|[marshal_context::marshal_context](#marshal-context)|Oluşturur bir `marshal_context` yönetilen ve yerel veri türleri arasında veri dönüştürme için kullanılacak nesne.| 
|[marshal_context::~marshal_context](#tilde-marshal-context)|Yok eder bir `marshal_context` nesne.| 

### <a name="public-methods"></a>Genel yöntemler

|Ad|Açıklama| 
|---------|-----------| 
|[marshal_context::marshal_as](#marshal-as)|Yönetilen ve yerel veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde sıralama gerçekleştirir.| 


## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="marshal-context"></a>marshal_context::marshal_context

Oluşturur bir `marshal_context` yönetilen ve yerel veri türleri arasında veri dönüştürme için kullanılacak nesne.

```cpp
marshal_context();
```

### <a name="remarks"></a>Açıklamalar

Bazı veri dönüştürme bir sıralama bağlamda gerektirir. Çevirileri olduğu hakkında daha fazla bilgi için bir bağlam gerektirir ve hangi hazırlama, dosya, uygulamanızda eklemeniz gerekir, bkz: [C++'da hazırlamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md).

### <a name="example"></a>Örnek

Örneğin bakın [marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md).


## <a name="tilde-marshal-context"></a>marshal_context:: ~ marshal_context

Yok eder bir `marshal_context` nesne.

```cpp
~marshal_context();
```

### <a name="remarks"></a>Açıklamalar

Bazı veri dönüştürme bir sıralama bağlamda gerektirir. Bkz: [C++'da hazırlamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md) hangi çevirileri bir bağlamda gerektirir ve uygulamanıza dahil edilecek hazırlama hangi dosya sahip hakkında daha fazla bilgi.

Silme bir `marshal_context` söz konusu bağlamdan dönüştürülen bir veri nesnesi geçersiz kılacak. Sonra verilerinizi korumak istiyorsanız bir `marshal_context` nesnesi yok edildiğinde, veriler korunur bir değişkene elle kopyalamanız gerekir.

## <a name="marshal-as"></a>marshal_context::marshal_as

Yönetilen ve yerel veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde sıralama gerçekleştirir.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>Parametreler

*Giriş*<br/>
[in] İçin hazırlamak istediğiniz değeri bir `To_Type` değişkeni.

### <a name="return-value"></a>Dönüş değeri

Türünde bir değişken `To_Type` dönüştürülmüş değeri olan `input`.

### <a name="remarks"></a>Açıklamalar

Bu işlev bir özel veri nesnesinde sıralama gerçekleştirir. Bu işlevi yalnızca tabloda belirtildiği dönüşümlü kullanın [C++'da hazırlamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md).

Bir çift desteklenmez, veri türleri sıralamanız çalışırsanız `marshal_as` bir hata oluşturur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) derleme zamanında. Daha fazla bilgi için bu hata ile sağlanmış bir iletiyi okuyun. `C4996` Hata birden fazla yalnızca kullanım dışı işlevler için oluşturulabilir. Bu hata üreten iki koşul hazırlarken bir çift desteklenmeyen veri türleri ve kullanmayı denemek `marshal_as` bir bağlam gerektiren bir dönüştürme için.

Sıralama Kitaplığı çeşitli üstbilgi dosyalarından oluşur. Herhangi bir dönüştürmeyi yalnızca bir dosya gerektirir, ancak diğer dönüştürmeleri için gerekiyorsa, ek dosyalar içerebilir. Tablodaki `Marshaling Overview in C++` hazırlama hangi dosya her dönüştürme için dahil edilmesi gereken gösterir.

### <a name="example"></a>Örnek

Bu örnek, gelen hazırlama için bir bağlam oluşturur. bir `System::String` için bir `const char *` değişken türü. Dönüştürülmüş veri bağlamını siler satırın sonunda geçerli olmaz.

```cpp
// marshal_context_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   marshal_context^ context = gcnew marshal_context();
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = context->marshal_as<const char*>( message );
   delete context;
   return 0;
}
```