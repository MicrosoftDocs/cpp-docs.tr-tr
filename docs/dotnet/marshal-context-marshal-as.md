---
title: marshal_context::marshal_as
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_context::marshal_as
- marshal_context.marshal_as
- msclr.interop.marshal_context.marshal_as
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 24a1afee-51c0-497c-948c-f77fe43635c8
ms.openlocfilehash: b097fda0870b2f49d4883e0fafd48f9637d28853
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649785"
---
# <a name="marshalcontextmarshalas"></a>marshal_context::marshal_as

Yönetilen ve yerel veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde sıralama gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>Parametreler

*Giriş*<br/>
[in] İçin hazırlamak istediğiniz değeri bir `To_Type` değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Türünde bir değişken `To_Type` dönüştürülmüş değeri diğer bir deyişle `input`.

## <a name="remarks"></a>Açıklamalar

Bu işlev bir özel veri nesnesinde sıralama gerçekleştirir. Bu işlevi yalnızca tabloda belirtildiği dönüşümlü kullanın [Overview of Marshaling c++](../dotnet/overview-of-marshaling-in-cpp.md).

Bir çift desteklenmeyen veri türleri sıralamanız çalışırsanız `marshal_as` bir hata oluşturur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) derleme zamanında. Daha fazla bilgi için bu hata ile sağlanmış bir iletiyi okuyun. `C4996` Hata birden fazla yalnızca kullanım dışı işlevler için oluşturulabilir. Bu hata üreten iki koşul hazırlarken bir çift desteklenmeyen veri türleri ve kullanmayı denemek `marshal_as` bir bağlam gerektiren bir dönüştürme için.

Sıralama Kitaplığı çeşitli üstbilgi dosyalarından oluşur. Herhangi bir dönüştürmeyi yalnızca bir dosya gerektirir, ancak diğer dönüştürmeleri için gerekiyorsa, ek dosyalar içerebilir. Tablodaki `Marshaling Overview in C++` hazırlama hangi dosya her dönüştürme için dahil edilmesi gereken gösterir.

## <a name="example"></a>Örnek

Bu örnek, gelen hazırlama için bir bağlam oluşturur. bir `System::String` için bir `const char *` değişken türü. Dönüştürülmüş veri bağlamını siler satırından sonra geçerli olmayacak.

```
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

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Ayrıca Bkz.

[Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_as](../dotnet/marshal-as.md)<br/>
[marshal_context Class](../dotnet/marshal-context-class.md)