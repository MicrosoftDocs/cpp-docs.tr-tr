---
title: '&lt;bit&gt;'
description: Tek tek bitleri ve bit dizilerini erişmek, işlemek ve işlemek için işlevler.
ms.date: 08/28/2020
f1_keywords:
- <bit>
helpviewer_keywords:
- bit header
ms.openlocfilehash: f9742ce1e15a817923c144544eb3bb6325e76765
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509960"
---
# <a name="ltbitgt"></a>&lt;bit&gt;

Tek tek bitleri ve bit dizilerini erişmek, işlemek ve işlemek için işlevleri tanımlar.

Örneğin, bitleri döndürme, ardışık küme veya temizlenmiş bitlerin sayısını bulma işlevleri mevcuttur, bir sayının iki integral gücü olup olmadığını, bir sayıyı temsil etmek için en az bit sayısını bulmayı ve bu şekilde devam ettiğini görün.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<bit>

**Ad alanı:** std

[/std: c + + en son](../build/reference/std-specify-language-standard-version.md) gereklidir.

## <a name="members"></a>Üyeler

### <a name="types"></a>Türler

| Tür | Açıklama |
|--------|----------|
| [endian](bit-enum.md) | Skaler türlerin bitiliğini belirtir. |

### <a name="functions"></a>İşlevler

| İşlev | Açıklama |
|-----|-----|
|[bit_cast](bit-functions.md#bit_cast) | Nesne temsilini bir türden diğerine yeniden yorumlayın. |
|[bit_ceil](bit-functions.md#bit_ceil) | İki değerden büyük veya eşit bir değere eşit olan en küçük kuvveti bulun. |
|[bit_floor](bit-functions.md#bit_floor) | İki değerin en büyük integral gücünü bir değerden daha büyük bir değere bulur. |
|[bit_width](bit-functions.md#bit_width) | Bir değeri temsil etmek için gereken en az bit sayısını bulun. |
|[countl_zero](bit-functions.md#countl_zero) | Ardışık bitlerin sayısını, en önemli bitten başlayarak sıfır olarak ayarlayın. |
|[countl_one](bit-functions.md#countl_one) | En önemli bitden başlayarak, birbirini izleyen ardışık bitlerin sayısını bir olarak ayarlayın. |
|[countr_zero](bit-functions.md#countr_zero) | En az önemli bitden başlayarak ardışık bitlerin sayısını sıfır olarak ayarlayın. |
|[countr_one](bit-functions.md#countl_one) | Ardışık olmayan bitlerin sayısını, en az önemli bir bitten başlayarak bir tane olarak ayarlayın. |
|[has_single_bit](bit-functions.md#has_single_bit) | Bir değerin tek bir bit kümesine sahip olup olmadığını denetleyin. Bu, bir değerin ikinin üssü olup olmadığını test etme ile aynıdır. |
|[popcount](bit-functions.md#popcount) | Bir olarak ayarlanan bit sayısını say. |
|[rotl](bit-functions.md#rotl) | Bit düzeyinde sola döndürmenin sonucunu hesaplama. |
|[rotr](bit-functions.md#rotr) | Bit düzeyinde sağa döndürmenin sonucunu hesaplama. |

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](cpp-standard-library-header-files.md)
