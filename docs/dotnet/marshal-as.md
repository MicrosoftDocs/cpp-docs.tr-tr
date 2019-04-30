---
title: marshal_as
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
ms.openlocfilehash: 2294d8fe94a32f281332c963b21a542366ae3207
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386089"
---
# <a name="marshalas"></a>marshal_as

Bu yöntem, yerel ve yönetilen ortamlar arasında verileri dönüştürür.

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

Bu yöntem, yerel ve yönetilen türleri arasında verileri dönüştürmek için basitleştirilmiş bir yoludur. Hangi veri türlerinin desteklendiğini belirlemek için bkz: [Overview of Marshaling c++](../dotnet/overview-of-marshaling-in-cpp.md). Bazı veri dönüştürme bir bağlamda gerektirir. Bu veri türlerini kullanarak dönüştürebilirsiniz [; marshal_context Class](../dotnet/marshal-context-class.md).

Bir çift desteklenmeyen veri türleri sıralamanız çalışırsanız `marshal_as` bir hata oluşturur [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) derleme zamanında. Daha fazla bilgi için bu hata ile sağlanmış bir iletiyi okuyun. `C4996` Hata birden fazla yalnızca kullanım dışı işlevler için oluşturulabilir. Desteklenmeyen veri türleri bir çift hazırlamak bunun bir örneği çalışıyor.

Sıralama Kitaplığı çeşitli üstbilgi dosyalarından oluşur. Herhangi bir dönüştürmeyi yalnızca bir dosya gerektirir, ancak diğer dönüştürmeleri için gerekiyorsa, ek dosyalar içerebilir. Tablodaki hangi dönüştürmeler hangi dosyalarıyla ilişkili olduğunu görmek için Ara `Marshaling Overview`. Yapmak istediğiniz hangi dönüştürülmesi bakılmaksızın, ad alanı her zaman etkin gereksinimidir.

## <a name="example"></a>Örnek

Bu örnek alanından sürekliliğe devreder bir `const char*` için bir `System::String` değişken türü.

```
// marshal_as_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   const char* message = "Test String to Marshal";
   String^ result;
   result = marshal_as<String^>( message );
   return 0;
}
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="see-also"></a>Ayrıca bkz.

[Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_context Class](../dotnet/marshal-context-class.md)
