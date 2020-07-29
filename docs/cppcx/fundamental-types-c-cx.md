---
title: Temel Türler (C++/CX)
ms.date: 01/22/2017
ms.assetid: c9f82907-25f2-440b-91d6-afb8dbd46ea6
ms.openlocfilehash: 3d484d9490a0a5b2ee2e7f92381528124b47701c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231006"
---
# <a name="fundamental-types-ccx"></a>Temel Türler (C++/CX)

C++/CX, Standart c++ yerleşik türlerine ek olarak, Standart c++ türleriyle eşlenen Windows çalışma zamanı temel türler için tür tanımları sağlayarak Windows çalışma zamanı mimarisi tarafından tanımlanan tür sistemini destekler. C++/CX Boolean, karakter ve sayısal temel türler uygular. Bu tür tanımları 'ler ad alanında tanımlanmıştır `default` , bu da hiçbir şekilde açıkça belirtilmelidir. Ayrıca, C++/CX, bazı Windows Çalışma Zamanı türleri ve arabirimleri için sarmalayıcılar ve somut uygulamalar sağlar.

## <a name="boolean-and-character-types"></a>Boole ve karakter türleri

Aşağıdaki tabloda yerleşik Boole ve karakter türleri ve bunların standart C++ eşdeğerleri listelenmektedir.

|Ad Alanı|C++/CX adı|Tanım|Standart C++ adı|Değer aralığı|
|---------------|-----------------------------------------------------------------------|----------------|-------------------------|---------------------|
|Platform|Boole|8 bit Boolean değeri.|bool|**`true`**(sıfır dışında) ve **`false`** (sıfır)|
|default|Char16|Unicode (UTF-16) kod noktasını temsil eden 16 bit sayısal olmayan bir değer.|wchar_t<br /><br /> -veya-<br /><br /> L'c '|(Unicode standardı tarafından belirtilen)|

## <a name="numeric-types"></a>Sayısal türler

Aşağıdaki tabloda yerleşik sayısal türler listelenmektedir. Sayısal türler `default` ad alanında belirtilir ve ilgili C++ yerleşik türü için tür tanımları ' dir. C++ yerleşik türlerinin tamamı (örneğin Long) Windows Çalışma Zamanı desteklenmez. Tutarlılık ve açıklık için C++/CX adını kullanmanızı öneririz.

|C++/CX adı|Tanım|Standart C++ adı|Değer aralığı|
|-----------------------------------------------------------------------|----------------|-------------------------|---------------------|
|int8|8 bit işaretli sayısal değer.|işaretli karakter|-128 ila 127|
|Uint8|8 bit işaretsiz sayısal değer.|unsigned char|0 ila 255|
|Int16|16 bit işaretli tamsayı.|short|-32.768 ila 32.767|
|Int16|16 bitlik işaretsiz tamsayı.|imzasız short|0 ila 65.535|
|Int32|32 bitlik işaretli tamsayı.|int|-2.147.483.648 ila 2.147.483.647|
|Int32|32 bitlik işaretsiz tamsayı.|unsigned int|0 ila 4.294.967.295|
|tutulamaz|64 bitlik işaretli tamsayı.|uzun uzun veya-__int64|-9.223.372.036.854, 775.808-9.223.372.036.854.775.807|
|Int64|64 bitlik işaretsiz tamsayı.|işaretsiz uzun uzun veya-işaretsiz __int64|0 ile 18446744073709551615 arası|
|float32|32 bitlik bir IEEE 754 kayan noktalı sayı.|float|3.4 e +/-38 (7 basamak)|
|float64|64 bitlik bir IEEE 754 kayan noktalı sayı.|double|1.7 e +/-308 (15 basamak)|

## <a name="windows-runtime-types"></a>Windows Çalışma Zamanı türleri

Aşağıdaki tabloda Windows Çalışma Zamanı mimarisi tarafından tanımlanan ve C++/CX' te yerleşik olan bazı ek türler listelenmektedir. Nesne ve dize başvuru türleridir. Diğerleri değer türlerdir. Bu türlerin tümü `Platform` ad alanında bildirilmiştir. Tam liste için bkz. [Platform ad alanı](../cppcx/platform-namespace-c-cx.md).

|Ad|Tanım|
|----------|----------------|
|Nesne|Tüm Windows Çalışma Zamanı türlerini temsil eder.|
|Dize|Metni temsil eden bir dizi karakter.|
|Rect|Bir dikdörtgenin konumunu ve boyutunu temsil eden dört kayan nokta sayısı kümesi.|
|SizeT|Bir yükseklik ve genişlik belirten sıralı bir kayan noktalı sayı çifti.|
|Seçeneğinin|İki boyutlu düzlemde bir noktayı tanımlayan sıralı bir kayan nokta x koordinatları ve y koordinatları çifti.|
|Guid|Benzersiz bir tanımlayıcı olarak kullanılan 128 bitlik sayısal olmayan bir değer.|
|UIntPtr|(Yalnızca iç kullanım için.) İşaretçi olarak kullanılan işaretsiz 64 bitlik bir değer.|
|Serisi|(Yalnızca iç kullanım için.)  İşaretçi olarak kullanılan işaretli 64 bitlik bir değer.|

## <a name="see-also"></a>Ayrıca bkz.

[Tür sistemi](../cppcx/type-system-c-cx.md)
