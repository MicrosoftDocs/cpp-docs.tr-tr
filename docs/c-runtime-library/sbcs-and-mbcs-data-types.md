---
title: SBCS ve MBCS Veri Türleri
ms.date: 04/11/2018
f1_keywords:
- MBCS
- SBCS
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
ms.openlocfilehash: 72215b7a3fff638daf02f136e3a107ce8a8a00d5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233918"
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS ve MBCS Veri Türleri

Yalnızca bir çok baytlı karakter veya çok baytlı bir karakterin bir baytını işleyen Microsoft MBCS çalışma zamanı kitaplığı yordamı bir **`unsigned int`** bağımsız değişken (0x00 <= karakter değeri <= 0xFFFF ve 0x00 <= Byte değeri <= 0xFF) bekler. Bir dize bağlamındaki çok baytlı baytları veya karakterleri işleyen bir MBCS yordamı, çok baytlı karakter dizesinin bir işaretçi olarak temsil olmasını bekler **`unsigned char`** .

> [!CAUTION]
> Çok baytlı bir karakterin her baytı, 8 bit içinde gösterilebilir **`char`** . Ancak, **`char`** 0x7F 'den büyük bir değere sahip olan BIR sbcs veya mbcs tek baytlık karakter negatif olur. Böyle bir karakter doğrudan bir veya a 'ya dönüştürüldüğünde **`int`** **`long`** , sonuç derleyici tarafından işaret genişletilir ve bu nedenle beklenmedik sonuçlara neden olabilir.

Bu nedenle, çok baytlı bir karakterin baytını 8 bit olarak temsil etmek en iyisidir **`unsigned char`** . Ya da, negatif bir sonuçtan kaçınmak için, tek baytlı bir karakteri bir **`char`** **`unsigned char`** veya bir öğesine dönüştürmeden önce türüne dönüştürmeniz yeterlidir **`int`** **`long`** .

Bazı SBCS dize işleme işlevleri (imzalı) parametre aldığı için **`char`** <strong>\*</strong> , **_MBCS** tanımlandığında bir tür uyuşmazlığı derleyici uyarısı oluşur. Verimlilik sırasıyla listelenen bu uyarıyı önlemenin üç yolu vardır:

1. TCHAR 'daki tür kullanımı uyumlu satır içi işlevleri kullanın. Olsun. Bu, varsayılan davranıştır.

1. TCHAR 'daki doğrudan makroları kullanın. H komutunu komut satırında tanımlayarak **_MB_MAP_DIRECT** . Bunu yaparsanız, türleri el ile eşleştirebilirsiniz. Bu en hızlı yöntemdir, ancak tür kullanımı güvenli değildir.

1. TCHAR 'daki tür kullanımı uyumlu statik bağlantılı kitaplık işlevlerini kullanın. Olsun. Bunu yapmak için, komut satırındaki sabit **_NO_INLINING** tanımlayın. Bu en yavaş yöntemdir, ancak tür açısından güvenlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
