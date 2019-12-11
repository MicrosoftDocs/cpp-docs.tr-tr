---
title: marshal_as
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
ms.openlocfilehash: 2b2cacb0acf04aa40b3e299bffd7357e04916b16
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988132"
---
# <a name="marshal_as"></a>marshal_as

Bu yöntem, verileri yerel ve yönetilen ortamlar arasında dönüştürür.

## <a name="syntax"></a>Sözdizimi

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>Parametreler

*girişinin*<br/>
'ndaki `To_Type` değişkenine sıralamak istediğiniz değer.

## <a name="return-value"></a>Dönüş Değeri

`input`dönüştürülmüş değeri olan `To_Type` türünde bir değişken.

## <a name="remarks"></a>Açıklamalar

Bu yöntem, yerel ve yönetilen türler arasında veri dönüştürmenin basitleştirilmiş bir yoludur. Hangi veri türlerinin desteklendiğini belirlemek için, bkz. [sıralamaya C++genel bakış ](../dotnet/overview-of-marshaling-in-cpp.md). Bazı veri dönüştürmeleri bir bağlam gerektirir. Bu veri türlerini [Marshal_context sınıfını](../dotnet/marshal-context-class.md)kullanarak dönüştürebilirsiniz.

Desteklenmeyen bir çift veri türü oluşturmayı denerseniz `marshal_as`, derleme zamanında bir hata [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) oluşturur. Daha fazla bilgi için bu hatayla sağlanan iletiyi okuyun. `C4996` hatası, yalnızca kullanım dışı bırakılmış işlevlerden daha fazla şekilde oluşturulabilir. Bunun bir örneği, desteklenmeyen bir veri türleri çiftini sıralamakta çalışıyor.

Sıralama kitaplığı, çeşitli üst bilgi dosyalarından oluşur. Herhangi bir dönüştürme yalnızca bir dosya gerektirir, ancak başka dönüştürmeler için gerekiyorsa ek dosyalar ekleyebilirsiniz. Hangi dosyaların hangi dosyalarla ilişkilendirildiğini görmek için `Marshaling Overview`' deki tabloya bakın. Yapmak istediğiniz dönüştürme ne olursa olsun, ad alanı gereksinimi her zaman etkindir.

Giriş parametresi null ise `System::ArgumentNullException(_EXCEPTION_NULLPTR)` oluşturur.

## <a name="example"></a>Örnek

Bu örnek, bir `const char*` `System::String` değişken türüne göre sıralar.

```cpp
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

**Üst bilgi dosyası:** \<msclr\marshal.h >, \<msclr \ marshal_windows. h >, \<msclr \ marshal_cppstd. h > veya \<msclr \ marshal_atl. h >

**Ad alanı:** msclr:: Interop

## <a name="see-also"></a>Ayrıca bkz.

[Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_context Class](../dotnet/marshal-context-class.md)
