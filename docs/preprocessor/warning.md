---
title: uyarı
ms.date: 11/04/2016
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragmas, warning
- push pragma warning
- pop warning pragma
- warning pragma
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
ms.openlocfilehash: 53f79061ded358c9cb895fd7e8e245c46ed99fd5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631731"
---
# <a name="warning-pragma"></a>warning Pragması
Derleyici uyarı iletilerini davranışını seçmeli değiştirilmesini sağlar.

## <a name="syntax"></a>Sözdizimi

```
#pragma warning(
    warning-specifier : warning-number-list [; warning-specifier : warning-number-list...] )
#pragma warning( push[ ,n ] )
#pragma warning( pop )
```

## <a name="remarks"></a>Açıklamalar

Aşağıdaki uyarı-specifier parametreleri büyük/küçük harf kullanılabilir.

|Uyarı tanımlayıcısı|Açıklama|
|------------------------|-------------|
|*1, 2, 3, 4*|Belirtilen düzeyi için belirtilen uyarı geçerlidir. Bu da varsayılan olarak kapalıdır belirtilen bir uyarı açar.|
|*default*|Uyarı davranışı, varsayılan değerine sıfırlayın. Bu da varsayılan olarak kapalıdır belirtilen bir uyarı açar. Uyarı, varsayılan olarak oluşturulan, belgelenen düzeyi.<br /><br /> Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../preprocessor/compiler-warnings-that-are-off-by-default.md).|
|*Devre dışı bırak*|Belirtilen uyarı iletileri sorun değil.|
|*Hata*|Belirtilen uyarıları hata olarak bildirin.|
|*once*|Belirtilen iletileri yalnızca bir kez görüntülenir.|
|*gösterme*|Yığına pragma geçerli durumunu, sonraki satır için belirtilen uyarı devre dışı bırakır ve böylece pragma durumu sıfırlama uyarısı yığın yığından açar.|

Aşağıdaki kod açıklaması gösterir bir `warning-number-list` birden çok uyarı numaralarını ve bu birden fazla parametre içerebilir `warning-specifier` parametreleri aynı pragma yönergesi belirtilebilir.

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

Bu aşağıdaki kodu işlevsel olarak eşdeğerdir.

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning 4385 only once.
#pragma warning( once : 4385 )

// Report warning 4164 as an error.
#pragma warning( error : 164 )
```

Derleyici 4000 0 ile 999 arasında herhangi bir uyarı numarası ekler.

Kod oluşturma ile ilişkili olduğundan, 4700-4999, aralıktaki uyarı numaralarını için yürürlükte derleyici işlevinin açık küme ayracı karşılaştığında uyarı durumuna işlevi geri kalanı için geçerli olacaktır. Kullanarak **uyarı** 4699 daha büyük bir sayı içeren bir uyarı durumunu değiştirmek için işlev pragması yalnızca olarak işlevin sonuna sonra geçerlilik kazanacaktır. Aşağıdaki örnek, doğru yerleşimini gösterir **uyarı** kod üretimi uyarı iletisi devre dışı bırakmak için pragmalar ve geri yüklemek için.

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

Bir işlev boyunca, son ayarını gövde dikkat edin **uyarı** pragma tüm işlevi için geçerli olacaktır.

## <a name="push-and-pop"></a>Anında iletme ve açılır

**Uyarı** pragması da destekler aşağıdaki sözdizimini, burada *n* uyarı düzeyi (1-4) temsil eder.

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

Pragma `warning( push )` her uyarı için geçerli bir uyarı durumu depolar. Pragma `warning( push, n )` her uyarı için geçerli durumunu depolar ve genel uyarı düzeyini ayarlar *n*.

Pragma `warning( pop )` POP son uyarı durumu, yığın üstüne gönderildi. Uyarı durumu arasında yapılan tüm değişiklikler *anında iletme* ve *pop* geri alınır. Bu örneği göz önünde bulundurun:

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

Bu kod, sonunda *pop* her uyarı durumunu geri yükler (4705 4706 ve 4707 içerir) için kod başlangıcında neydi.

Üst bilgi dosyaları yazdığınızda, kullanabileceğiniz *anında iletme* ve *pop* bir kullanıcı tarafından yapılan bir uyarı durumu değişiklikleri üstbilgileri doğru derleme engellemez olduğunu garanti etmek için. Kullanım *anında iletme* başlangıç başlığının ve *pop* sonunda. Örneğin, düzgün bir şekilde 4 uyarı düzeyinde derleyin değil bir üstbilgi varsa, aşağıdaki kod uyarı düzeyini 3 olarak değiştirmek ve sonra özgün uyarı düzeyi üst sonunda geri yükleyin.

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

Uyarı, derleyici yardımcı olan seçeneklerdir gösterme hakkında daha fazla bilgi için bkz [/FI](../build/reference/fi-name-forced-include-file.md) ve [/w](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)