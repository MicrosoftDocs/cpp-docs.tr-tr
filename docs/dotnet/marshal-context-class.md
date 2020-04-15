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
ms.openlocfilehash: 110fe4abf7eb90b05e7feef563efa4882bed0fc6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332005"
---
# <a name="marshal_context-class"></a>marshal_context Sınıfı

Bu sınıf, verileri yerel ve yönetilen ortamlar arasında dönüştürür.

## <a name="syntax"></a>Sözdizimi

```cpp
class marshal_context
```

## <a name="remarks"></a>Açıklamalar

Bağlam `marshal_context` gerektiren veri dönüşümleri için sınıfı kullanın. Hangi dönüşümlerin bir bağlam gerektirdiği ve hangi dosyalama dosyasının eklenmesi gerektiği hakkında daha fazla bilgi için [bkz.](../dotnet/overview-of-marshaling-in-cpp.md) Bir bağlam kullandığınızda mareşallik sonucu yalnızca `marshal_context` nesne yok edilene kadar geçerlidir. Sonucunuzu korumak için verileri kopyalamanız gerekir.

Aynı `marshal_context` durum çok sayıda veri dönüşümü için de kullanılabilir. Bağlamı bu şekilde yeniden kullanmak, önceki mareşal aramalarından elde edilen sonuçları etkilemez.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Kamu yapıcılar

|Adı|Açıklama|
|---------|-----------|
|[marshal_context::marshal_context](#marshal-context)|Yönetilen ve `marshal_context` yerel veri türleri arasında veri dönüştürme için kullanılacak bir nesne oluşturuyor.|
|[marshal_context::~marshal_context](#tilde-marshal-context)|Bir `marshal_context` nesneyi yok eder.|

### <a name="public-methods"></a>Genel yöntemler

|Adı|Açıklama|
|---------|-----------|
|[marshal_context::marshal_as](#marshal-as)|Yönetilen ve yerel bir veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde mareşal gerçekleştirir.|

## <a name="requirements"></a>Gereksinimler

**Başlık dosyası:** \<msclr\marshal.h \<>, msclr\marshal_windows.h>, \<msclr\marshal_cppstd.h> veya \<msclr\marshal_atl.h>

**İsim alanı:** msclr::interop

## <a name="marshal_contextmarshal_context"></a><a name="marshal-context"></a>marshal_context:marshal_context

Yönetilen ve `marshal_context` yerel veri türleri arasında veri dönüştürme için kullanılacak bir nesne oluşturuyor.

```cpp
marshal_context();
```

### <a name="remarks"></a>Açıklamalar

Bazı veri dönüşümleri bir mareşal bağlamı gerektirir. Hangi çevirilerin bir bağlam gerektirdiği ve uygulamanıza hangi dosyalama dosyasını eklemeniz gerektiği hakkında daha fazla bilgi için [Bkz.](../dotnet/overview-of-marshaling-in-cpp.md)

### <a name="example"></a>Örnek

marshal_context örneğine [bakın:marshal_as](../dotnet/marshal-context-marshal-as.md).

## <a name="marshal_contextmarshal_context"></a><a name="tilde-marshal-context"></a>marshal_context::~marshal_context

Bir `marshal_context` nesneyi yok eder.

```cpp
~marshal_context();
```

### <a name="remarks"></a>Açıklamalar

Bazı veri dönüşümleri bir mareşal bağlamı gerektirir. Hangi çevirilerin bir bağlam gerektirdiği ve uygulamanıza hangi dosyalama dosyasının eklenmesi gerektiği hakkında daha fazla bilgi için [C++'da mareşallik](../dotnet/overview-of-marshaling-in-cpp.md) genel görünümüne bakın.

Bir `marshal_context` nesneyi silerken, bu bağlam tarafından dönüştürülen verileri geçersiz kılın. Bir `marshal_context` nesne yok edildikten sonra verilerinizi korumak istiyorsanız, verilerinizi kalıcı bir değişkene el ile kopyalamanız gerekir.

## <a name="marshal_contextmarshal_as"></a><a name="marshal-as"></a>marshal_context:marshal_as

Yönetilen ve yerel bir veri türü arasında dönüştürmek için belirli bir veri nesnesi üzerinde mareşal gerçekleştirir.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>Parametreler

*Giriş*<br/>
[içinde] Bir `To_Type` değişkene almak istediğiniz değer.

### <a name="return-value"></a>Döndürülen değer

Dönüştürülen değeri `To_Type` olan bir tür değişkeni. `input`

### <a name="remarks"></a>Açıklamalar

Bu işlev, belirli bir veri nesnesi üzerinde mareşal gerçekleştirir. Bu işlevi yalnızca [C++'da mareşallik genel bakışı](../dotnet/overview-of-marshaling-in-cpp.md)tablosunda gösterilen dönüşümlerle kullanın.

Desteklenmeyen bir çift veri türünü deftere göremeye `marshal_as` çalışırsanız, derleme zamanında [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) hatası oluşturur. Daha fazla bilgi için bu hatayı sağlayan iletiyi okuyun. Hata, `C4996` amortismana alınan işlevlerden daha fazlası için oluşturulabilir. Bu hatayı oluşturan iki koşul, desteklenmeyen bir çift veri türünü dağıtmaya `marshal_as` çalışmak ve bağlam gerektiren bir dönüştürme için kullanmaya çalışmak.

Mareşal kitaplığı birkaç üstbilgi dosyasından oluşur. Herhangi bir dönüştürme yalnızca bir dosya gerektirir, ancak diğer dönüşümler için gerekirse ek dosyalar ekleyebilirsiniz. Tablo, `Marshaling Overview in C++` her dönüşüm için hangi dosyalama dosyasının dahil edilmesi gerektiğini gösterir.

### <a name="example"></a>Örnek

Bu örnek, bir `System::String` değişken türünden bir `const char *` değişken türüne marshaling için bir bağlam oluşturur. Dönüştürülen veriler, bağlamı silen satırdan sonra geçerli olmaz.

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
