---
description: 'Daha fazla bilgi edinin: Warning pragma'
title: warning pragması
ms.date: 08/29/2019
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
ms.openlocfilehash: ac810076d1db0c975d28bc64d0a6d761c9cec608
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193116"
---
# <a name="warning-pragma"></a>warning pragması

Derleyici uyarı iletilerinin davranışının seçmeli olarak değiştirilmesine izin vermez.

## <a name="syntax"></a>Syntax

> **#pragma Uyarısı (**\
> &nbsp;&nbsp;&nbsp;&nbsp;*Uyarı belirleyicisi* **:** *Uyarı-sayı-liste*\
> &nbsp;&nbsp;&nbsp;&nbsp;[**;** *uyarı-tanımlayıcı* **:** *Uyarı-sayı-liste* ...] **)**\
> **#pragma Uyarısı (gönderim** [ **,** *n* ] **)**\
> **#pragma Uyarısı (pop)**

## <a name="remarks"></a>Açıklamalar

Aşağıdaki uyarı belirleyicisi parametreleri kullanılabilir.

|Uyarı Belirleyicisi|Anlamı|
|------------------------|-------------|
|*1, 2, 3, 4*|Verilen düzeyi belirtilen uyarıya Uygula. Ayrıca, varsayılan olarak kapalı olan belirli bir uyarıyı açar.|
|*varsayılanını*|Uyarı davranışını varsayılan değerine sıfırlayın. Ayrıca, varsayılan olarak kapalı olan belirli bir uyarıyı açar. Uyarı varsayılan, belgelenmiş, ve düzeyinde oluşturulacaktır.<br /><br /> Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../preprocessor/compiler-warnings-that-are-off-by-default.md).|
|*dıı*|Belirtilen uyarı iletilerini verme.|
|*hatayla*|Belirtilen uyarıları hata olarak raporla.|
|*tek*|Belirtilen iletileri yalnızca bir kez görüntüle.|
|*Gizle*|Yığında pragma 'ın geçerli durumunu gönderir, sonraki satır için belirtilen uyarıyı devre dışı bırakır ve sonra, pragma durumunun sıfırlanması için uyarı yığınını açılır.|

Aşağıdaki kod bildiriminde, bir `warning-number-list` parametrenin birden çok uyarı numarası içerebileceğini ve `warning-specifier` aynı pragma yönergesinde birden çok parametrenin belirtilebildiği gösterilmektedir.

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

Kod oluşturma ile ilişkili olanlar olan 4700-4999 aralığındaki uyarı numaraları için, derleyici işlev tanımıyla karşılaştığında geçerli olan uyarının durumu işlevin geri kalanı için geçerli olacaktır. 4699 'den büyük bir uyarı numarasının durumunu değiştirmek için işlevindeki **Uyarı** pragma kullanımı, yalnızca işlevin sonundan sonra devreye girer. Aşağıdaki örnek, kod oluşturma uyarı iletisini devre dışı bırakmak ve sonra geri yüklemek için **Uyarı** pragmaların doğru yerleşimini gösterir.

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

Bir işlev gövdesinde, **Uyarı** pragması 'nın son ayarının tüm işlev için geçerli olacağını unutmayın.

## <a name="push-and-pop"></a>Basma ve pop

**Uyarı** pragması aşağıdaki sözdizimini da destekler, burada *n* bir uyarı düzeyini (1 ile 4 arasında) temsil eder.

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

Pragma, `warning( push )` her uyarı için geçerli uyarı durumunu depolar. Pragma `warning( push, n )` her uyarı için geçerli durumu depolar ve genel uyarı düzeyini *n* olarak ayarlar.

Pragma, `warning( pop )` yığın üzerine gönderilen son uyarı durumunu yükler. Uyarı durumunda *Push* ve *pop* arasında yaptığınız tüm değişiklikler geri alınır. Bu örneği ele alalım:

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

Bu kodun sonunda, *pop* her uyarının durumunu (4705, 4706 ve 4707 içerir) kodun başlangıcında olduğu gibi geri yükler.

Üst bilgi dosyalarını yazdığınızda, bir kullanıcı tarafından yapılan uyarı durumu değişikliklerinin doğru bir şekilde derlenmeden emin olmak için *Push* ve *pop* kullanabilirsiniz. Üstbilginin başlangıcında *Gönder* ' i ve sonuna *açılan pencereyi* kullanın. Örneğin, uyarı düzeyi 4 ' te düzgün şekilde derlenmeyen bir üst bilgi varsa, aşağıdaki kod uyarı düzeyini 3 olarak değiştirir ve sonra üstbilginin sonundaki orijinal uyarı düzeyini geri yükler.

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

Uyarıları bastıralmanıza yardımcı olan derleyici seçenekleri hakkında daha fazla bilgi için bkz. [/Fi](../build/reference/fi-name-forced-include-file.md) ve [/w](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
