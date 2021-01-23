---
title: Warning pragma
description: Microsoft C/C++ uyarısı hakkında daha fazla bilgi edinin pragma
ms.date: 01/22/2021
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragma, warning
- push pragma warning
- pop warning pragma
- warning pragma
no-loc:
- pragma
ms.openlocfilehash: 97d48acc3c0e4651d3b05c0a6405d5c9c2031cf6
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712849"
---
# <a name="warning-no-locpragma"></a>`warning` pragma

Derleyici uyarı iletilerinin davranışının seçmeli olarak değiştirilmesine izin vermez.

## <a name="syntax"></a>Syntax

> **`#pragma warning(`**\
> &nbsp;&nbsp;&nbsp;&nbsp;*`warning-specifier`* **`:`** *`warning-number-list`*\
> &nbsp;&nbsp;&nbsp;&nbsp;[**`;`** *`warning-specifier`* **`:`** *`warning-number-list`* ... ] **`)`**\
> **`#pragma warning( push`** [ **`,`** *n* ] **`)`**\
> **`#pragma warning( pop )`**

## <a name="remarks"></a>Açıklamalar

Aşağıdaki uyarı belirleyicisi parametreleri kullanılabilir.

| Uyarı Belirleyicisi | Anlamı |
|--|--|
| `1`, `2`, `3`, `4` | Verilen düzeyi belirtilen uyarılara uygulayın. Ayrıca, varsayılan olarak kapalı olan belirli bir uyarıyı açar. |
| `default` | Uyarı davranışını varsayılan değerine sıfırlayın. Ayrıca, varsayılan olarak kapalı olan belirli bir uyarıyı açar. Uyarı varsayılan, belgelenmiş, ve düzeyinde oluşturulacaktır.<br /><br /> Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../preprocessor/compiler-warnings-that-are-off-by-default.md). |
| `disable` | Belirtilen uyarı iletilerini verme. |
| `error` | Belirtilen uyarıları hata olarak raporla. |
| `once` | Belirtilen iletileri yalnızca bir kez görüntüle. |
| `suppress` | Yığın üzerindeki geçerli durumunu gönderir pragma , sonraki satır için belirtilen uyarıyı devre dışı bırakır ve sonra durumun sıfırlanması için uyarı yığınını açılır pragma . |

Aşağıdaki kod bildiriminde bir *`warning-number-list`* parametrenin birden çok uyarı numarası içerebileceğini ve *`warning-specifier`* aynı yönergede birden çok parametrenin belirtilebildiği gösterilmektedir pragma .

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

Bu yönerge, aşağıdaki kod ile işlevsel olarak eşdeğerdir:

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning C4385 only once.
#pragma warning( once : 4385 )

// Report warning C4164 as an error.
#pragma warning( error : 164 )
```

Derleyici, 0 ile 999 arasında herhangi bir uyarı numarasına 4000 ekler.

4700-4999 aralığındaki uyarı numaraları kod oluşturma ile ilişkilidir. Bu uyarılar için, derleyici işlev tanımına ulaştığında işlevin geri kalanı için geçerli olan uyarının durumu geçerli olur. **`warning`** pragma İşlevindeki bir uyarı 4699 numarasının durumunu değiştirmek için işlevinin kullanımı, yalnızca işlevin sonundan sonra devreye girer. Aşağıdaki örnek, bir **`warning`** pragma kod oluşturma uyarı iletisini devre dışı bırakmak ve sonra geri yüklemek için öğesinin doğru yerleşimini gösterir.

```cpp
// pragma_warning.cpp
// compile with: /W1
#pragma warning(disable:4700)
void Test() {
   int x;
   int y = x;   // no C4700 here
   #pragma warning(default:4700)   // C4700 enabled after Test ends
}

int main() {
   int x;
   int y = x;   // C4700
}
```

Bir işlev gövdesinde, öğesinin son ayarının **`warning`** pragma tüm işlev için geçerli olacağını unutmayın.

## <a name="push-and-pop"></a>Basma ve pop

**`warning`** pragma Ayrıca, isteğe bağlı *n* parametresi bir uyarı düzeyini (1 ile 4 arasında) temsil eden aşağıdaki sözdizimini destekler.

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

pragma `warning( push )` Her uyarı için geçerli uyarı durumunu depolar. pragma `warning( push, n )` Her uyarı için geçerli durumu depolar ve genel uyarı düzeyini *n* olarak ayarlar.

pragma `warning( pop )` Son uyarı durumu, yığın üzerine gönderilir. Ve arasında uyarı durumunda yaptığınız tüm değişiklikler `push` `pop` geri alınır. Bu örneği ele alalım:

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

Bu kodun sonunda, kodun başlangıcında olduğu gibi, `pop` her uyarının durumunu (4705, 4706 ve 4707 içerir) geri yükler.

Üst bilgi dosyalarını yazdığınızda, `push` `pop` bir kullanıcı tarafından yapılan uyarı durumu değişikliklerinin doğru bir şekilde derlenmeyeceği garantisi vermek için ve kullanabilirsiniz. `push`Üstbilginin başlangıcında ve `pop` sonunda kullanın. Örneğin, uyarı düzeyi 4 ' te düzgün bir şekilde derlenmeyen bir üstbilgiye sahip olabilirsiniz. Aşağıdaki kod, uyarı düzeyini 3 olarak değiştirir ve sonra üstbilginin sonundaki orijinal uyarı düzeyini geri yükler.

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

Uyarıları bastıralmanıza yardımcı olan derleyici seçenekleri hakkında daha fazla bilgi için bkz [`/FI`](../build/reference/fi-name-forced-include-file.md) [`/w`](../build/reference/compiler-option-warning-level.md) . ve.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
