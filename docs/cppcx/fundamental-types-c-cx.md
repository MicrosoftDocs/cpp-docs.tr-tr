---
title: Temel türler (C + +/ CX)
ms.date: 01/22/2017
ms.assetid: c9f82907-25f2-440b-91d6-afb8dbd46ea6
ms.openlocfilehash: a6c068d58f0d7c173bff34726873b7a0f4f1d74c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529135"
---
# <a name="fundamental-types-ccx"></a>Temel türler (C + +/ CX)

Ek standart C++ yerleşik türleri, C + +/ CX destekleyen standart C++ türlerini eşleştiren Windows çalışma zamanı temel türler için tür tanımları sağlayarak bir Windows çalışma zamanı mimari tarafından tanımlanan bir tür sistemi... C + +/ CX, Boolean, karakter ve sayısal temel türler uygular. Bu tür tanımlarından tanımlanan `default` ad alanı hiçbir zaman açıkça belirtilmesi gerekir. Ayrıca, C + +/ CX, sarmalayıcılar ve somut uygulamalarını belirli Windows çalışma zamanı türleri ve arabirimleri sağlar.

## <a name="boolean-and-character-types"></a>Boole ve karakter türleri

Aşağıdaki tabloda, yerleşik Boolean ve karakter türleri ve standart C++ eşdeğerleri listelenmektedir.

|Ad Alanı|C + +/ CX adı|Tanım|Standart C++ adı|Değer aralıkları|
|---------------|-----------------------------------------------------------------------|----------------|-------------------------|---------------------|
|Platform|Boole değeri|Bir 8 bit Boole değeri.|bool|**doğru** (sıfırdan farklı) ve **false** (sıfır)|
|default|char16|Bir Unicode (UTF-16) kod noktasını temsil eden bir 16-bit sayısal olmayan değer.|wchar_t<br /><br /> veya<br /><br /> L'c'|(Unicode standardı tarafından belirtilen)|

## <a name="numeric-types"></a>Sayısal türler

Aşağıdaki tabloda yerleşik sayısal türler listeler. Sayısal türlerin bildirilen `default` karşılık gelen C++ yerleşik türü için ad alanı ve bu tür tanımları. Windows çalışma zamanı'nda tüm C++ yerleşik türlerine (örneğin, uzun) desteklenir. Açıklık ve tutarlılık, C + kullanmanızı öneririz +/ CX adı.

|C + +/ CX adı|Tanım|Standart C++ adı|Değer aralıkları|
|-----------------------------------------------------------------------|----------------|-------------------------|---------------------|
|Int8|Bir 8 bit işaretli sayısal değer.|İmzalı char|-128 ile 127|
|uint8|Bir 8 bit işaretsiz sayısal değer.|unsigned char|0 ile 255|
|Int16|Bir 16 bitlik işaretli tamsayı.|short|-32.768 32.767 aracılığıyla|
|uint16|Bir 16 bitlik işaretsiz tamsayı.|imzasız short|0 ile 65.535|
|Int32|32-bit işaretli tamsayı.|int|-2.147.483.648 ile 2.147.483.647|
|uint32|32-bit işaretsiz bir tamsayı.|unsigned int|0'dan 4.294.967.295'e kadar|
|Int64|64-bit imzalı bir tamsayı.|Long long - veya - __int64|-9,223,372,036,854, 775,808 9.223.372.036.854.775.807 aracılığıyla|
|uint64|64-bit işaretsiz bir tamsayı.|İmzasız uzun uzun - veya - unsigned __int64|0 ile 18,446,744,073,709,551,615|
|float32|Bir 32-bit IEEE 754 kayan noktalı sayı.|float|3.4e +/-38 (7 basamak)|
|float64|Bir 64-bit IEEE 754 kayan noktalı sayı.|çift|1.7E +/-308 (15 basamak)|

## <a name="windows-runtime-types"></a>Windows çalışma zamanı türleri

Bir Windows çalışma zamanı mimari tarafından tanımlanır ve C + içinde yerleşik olan bazı ek türleri aşağıdaki tabloda listelenmektedir +/ CX. Nesne ve dize başvuru türleridir. Diğerleri, değer türleridir. Tüm bu tür içinde bildirilir `Platform` ad alanı. Tam bir listesi için bkz [Platform ad alanı](../cppcx/platform-namespace-c-cx.md).

|Ad|Tanım|
|----------|----------------|
|Nesne|Herhangi bir Windows çalışma zamanı türü temsil eder.|
|Dize|Bir metin temsil eden bir karakter dizisi.|
|Rect|Bir dikdörtgen boyutunu ve konumunu temsil eden dört kayan noktalı sayıların kümesi.|
|SizeT|Sıralı bir çift kayan noktalı sayıların yükseklik ve genişlik belirtin.|
|Noktası|Sıralı bir çift iki boyutlu bir düzleminde bir nokta tanımlayan y koordinatları ve kayan nokta x koordinatları.|
|Guid|Benzersiz bir tanımlayıcı olarak kullanılan bir 128-bit sayısal olmayan değer.|
|UIntPtr|(Yalnızca iç kullanım için.) Bir işaretçi olarak kullanılan bir işaretsiz 64-bit değeri.|
|IntPtr|(Yalnızca iç kullanım için.)  Bir işaretçi olarak kullanılan 64-bit imzalı bir değer.|

## <a name="see-also"></a>Ayrıca Bkz.

[Tür Sistemi](../cppcx/type-system-c-cx.md)