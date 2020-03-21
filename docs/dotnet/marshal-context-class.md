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
ms.openlocfilehash: 7fb22754248e66d7a20292af41a8e1b8ba050451
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80080026"
---
# <a name="marshal_context-class"></a>marshal_context Sınıfı

Bu sınıf, verileri yerel ve yönetilen ortamlar arasında dönüştürür.

## <a name="syntax"></a>Sözdizimi

```cpp
class marshal_context
```

## <a name="remarks"></a>Açıklamalar

Bağlam gerektiren veri dönüştürmeleri için `marshal_context` sınıfını kullanın. Hangi dönüştürmelerin bağlam gerektirdiğini ve hangi sıralama dosyasının dahil edileceğini hakkında daha fazla bilgi için bkz. [ C++sıralamaya genel bakış ](../dotnet/overview-of-marshaling-in-cpp.md). Bağlam kullandığınızda sıralama sonucu yalnızca `marshal_context` nesnesi yok edilene kadar geçerlidir. Sonucu korumak için verileri kopyalamanız gerekir.

Aynı `marshal_context` çok sayıda veri dönüştürmesi için de kullanılabilir. Bağlam bu şekilde yeniden kullanmak, önceki sıralama çağrılarındaki sonuçları etkilemez.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak oluşturucular

|Adı|Açıklama|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|Yönetilen ve yerel veri türleri arasında veri dönüştürme için kullanılacak bir `marshal_context` nesnesi oluşturur.|
|[marshal_context::~marshal_context](#tilde-marshal-context)|`marshal_context` nesnesini yok eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|Yönetilen ve yerel bir veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde sıralama gerçekleştirir.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası:** \<msclr\marshal.h >, \<msclr \ marshal_windows. h >, \<msclr \ marshal_cppstd. h > veya \<msclr \ marshal_atl. h >

**Ad alanı:** msclr:: Interop

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a>marshal_context:: marshal_context

Yönetilen ve yerel veri türleri arasında veri dönüştürme için kullanılacak bir `marshal_context` nesnesi oluşturur.

```cpp
marshal_context();
```

### <a name="remarks"></a>Açıklamalar

Bazı veri dönüştürmeleri bir sıralama bağlamı gerektirir. Hangi çevirilerin bağlam gerektirdiğini ve uygulamanıza dahil etmeniz gereken dosyayı sıralama hakkında daha fazla bilgi için bkz. [ C++sıralamaya genel bakış ](../dotnet/overview-of-marshaling-in-cpp.md).

### <a name="example"></a>Örnek

[Marshal_context:: marshal_as](../dotnet/marshal-context-marshal-as.md)için örneğe bakın.

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a>marshal_context:: ~ marshal_context

`marshal_context` nesnesini yok eder.

```cpp
~marshal_context();
```

### <a name="remarks"></a>Açıklamalar

Bazı veri dönüştürmeleri bir sıralama bağlamı gerektirir. Hangi çevirilerin bağlam gerektirdiğini ve uygulamanıza eklenmesi gereken sıralama dosyasını öğrenmek için bkz. [ C++ sıralamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md) .

Bir `marshal_context` nesnenin silinmesi, bu bağlam tarafından dönüştürülen verileri geçersiz kılar. `marshal_context` nesnesi yok edildikten sonra verilerinizi korumak istiyorsanız, verileri kalıcı olacak bir değişkene el ile kopyalamanız gerekir.

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a>marshal_context:: marshal_as

Yönetilen ve yerel bir veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde sıralama gerçekleştirir.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>Parametreler

*girişinin*<br/>
'ndaki `To_Type` değişkenine sıralamak istediğiniz değer.

### <a name="return-value"></a>Dönüş değeri

`input`dönüştürülmüş değeri olan `To_Type` türünde bir değişken.

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirli bir veri nesnesi üzerinde sıralama gerçekleştirir. Bu işlevi yalnızca, [içindeki C++sıralamaya genel bakış ](../dotnet/overview-of-marshaling-in-cpp.md)içindeki tablo tarafından belirtilen dönüştürmelerde kullanın.

Desteklenmeyen bir çift veri türü oluşturmayı denerseniz `marshal_as`, derleme zamanında bir hata [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) oluşturur. Daha fazla bilgi için bu hatayla sağlanan iletiyi okuyun. `C4996` hatası, yalnızca kullanım dışı bırakılmış işlevlerden daha fazla şekilde oluşturulabilir. Bu hatayı oluşturan iki koşul, desteklenmeyen bir veri türü çifti oluşturmaya çalışıyor ve bağlam gerektiren bir dönüştürme için `marshal_as` kullanmaya çalışıyor.

Sıralama kitaplığı, çeşitli üst bilgi dosyalarından oluşur. Herhangi bir dönüştürme yalnızca bir dosya gerektirir, ancak başka dönüştürmeler için gerekiyorsa ek dosyalar ekleyebilirsiniz. `Marshaling Overview in C++` tablo, her dönüştürme için hangi sıralama dosyasının ekleneceğini gösterir.

### <a name="example"></a>Örnek

Bu örnek, bir `System::String` `const char *` değişken türüne sıralama için bir bağlam oluşturur. Dönüştürülmüş veriler, bağlamı silen satırdan sonra geçerli olmayacaktır.

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