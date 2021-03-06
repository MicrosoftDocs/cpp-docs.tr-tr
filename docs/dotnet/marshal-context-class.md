---
description: 'Hakkında daha fazla bilgi edinin: marshal_context sınıfı'
title: marshal_context Sınıfı
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- msclr::marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 6fa625ed52ac69682574d52c423e54d200461e73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253661"
---
# <a name="marshal_context-class"></a>marshal_context Sınıfı

Bu sınıf, verileri yerel ve yönetilen ortamlar arasında dönüştürür.

## <a name="syntax"></a>Syntax

```cpp
class marshal_context
```

## <a name="remarks"></a>Açıklamalar

`marshal_context`Bağlam gerektiren veri dönüştürmeleri için sınıfını kullanın. Hangi dönüştürmelerin bağlam gerektirdiğini ve hangi sıralama dosyasının dahil edileceğini hakkında daha fazla bilgi için bkz. [C++ ' da sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md). Bağlam kullandığınızda sıralama sonucu yalnızca `marshal_context` nesne yok edilene kadar geçerlidir. Sonucu korumak için verileri kopyalamanız gerekir.

Aynı, `marshal_context` çok sayıda veri dönüştürmesi için de kullanılabilir. Bağlam bu şekilde yeniden kullanmak, önceki sıralama çağrılarındaki sonuçları etkilemez.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak oluşturucular

|Ad|Açıklama|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|`marshal_context`Yönetilen ve yerel veri türleri arasında veri dönüştürme için kullanılacak bir nesne oluşturur.|
|[marshal_context:: ~ marshal_context](#tilde-marshal-context)|Bir nesneyi yok eder `marshal_context` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|Yönetilen ve yerel bir veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde sıralama gerçekleştirir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası:** \<msclr\marshal.h> , \<msclr\marshal_windows.h> , \<msclr\marshal_cppstd.h> veya \<msclr\marshal_atl.h>

**Ad alanı:** msclr:: Interop

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a> marshal_context:: marshal_context

`marshal_context`Yönetilen ve yerel veri türleri arasında veri dönüştürme için kullanılacak bir nesne oluşturur.

```cpp
marshal_context();
```

### <a name="remarks"></a>Açıklamalar

Bazı veri dönüştürmeleri bir sıralama bağlamı gerektirir. Hangi çevirilerin bağlam gerektirdiğini ve uygulamanıza eklemeniz gereken dosyayı sıralama hakkında daha fazla bilgi için bkz. [C++ ' da sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md).

### <a name="example"></a>Örnek

[Marshal_context:: marshal_as](#marshal-as)için örneğe bakın.

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a> marshal_context:: ~ marshal_context

Bir nesneyi yok eder `marshal_context` .

```cpp
~marshal_context();
```

### <a name="remarks"></a>Açıklamalar

Bazı veri dönüştürmeleri bir sıralama bağlamı gerektirir. Hangi çevirilerin bağlam gerektirdiğini ve uygulamanıza hangi sıralama dosyasının dahil edileceğini öğrenmek için bkz. [C++ ' da sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md) .

Bir nesnenin silinmesi, `marshal_context` Bu bağlam tarafından dönüştürülen verileri geçersiz kılar. Bir nesne yok edildikten sonra verilerinizi korumak istiyorsanız `marshal_context` , verileri kalıcı olacak bir değişkene el ile kopyalamanız gerekir.

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a> marshal_context:: marshal_as

Yönetilen ve yerel bir veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde sıralama gerçekleştirir.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>Parametreler

*girişinin*<br/>
'ndaki Bir değişkene sıralamak istediğiniz değer `To_Type` .

### <a name="return-value"></a>Döndürülen değer

`To_Type`Dönüştürülmüş değeri olan türünde bir değişken `input` .

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirli bir veri nesnesi üzerinde sıralama gerçekleştirir. Bu işlevi yalnızca [C++ ' ta sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md)içindeki tablo tarafından belirtilen dönüştürmelerde kullanın.

Desteklenmeyen bir veri türleri çiftini sıralamakta çalışırsanız, `marshal_as` derleme zamanında bir [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) hatası oluşturur. Daha fazla bilgi için bu hatayla sağlanan iletiyi okuyun. `C4996`Hata, yalnızca kullanım dışı bırakılmış işlevlerden daha fazla şekilde oluşturulabilir. Bu hatayı oluşturan iki koşul, desteklenmeyen bir veri türü çifti oluşturmaya çalışıyor ve `marshal_as` bağlam gerektiren bir dönüştürme için kullanılmaya çalışıyor.

Sıralama kitaplığı, çeşitli üst bilgi dosyalarından oluşur. Herhangi bir dönüştürme yalnızca bir dosya gerektirir, ancak başka dönüştürmeler için gerekiyorsa ek dosyalar ekleyebilirsiniz. İçindeki tablosu, `Marshaling Overview in C++` her dönüştürme için hangi sıralama dosyasının ekleneceğini gösterir.

### <a name="example"></a>Örnek

Bu örnek, öğesinden bir değişken türüne sıralama için bir bağlam oluşturur `System::String` `const char *` . Dönüştürülmüş veriler, bağlamı silen satırdan sonra geçerli olmayacaktır.

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
