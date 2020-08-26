---
title: /HIGHENTROPYVA
ms.date: 06/12/2018
f1_keywords:
- /HIGHENTROPYVA
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
ms.openlocfilehash: 80e34a3f57974e1af6afb65196697cce9aa344b1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835005"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Yürütülebilir resmin yüksek entrolebilir 64 bit adres alanı düzeni rastgele seçimini (ASLR) destekleyip desteklemediğini belirtir.

## <a name="syntax"></a>Syntax

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>Açıklamalar

Bu seçenek *executable image* *`.dll`* *`.exe`* , 64 bitlik adres ASLR desteğini göstermek için yürütülebilir bir görüntü dosyasının (örneğin, bir veya dosyanın) üst bilgisini değiştirir. Bir etkiye sahip olmak için, hem çalıştırılabilir hem de bağımlı olduğu tüm modüller üzerinde seçeneğini ayarlayın. Ardından 64-bit ASLR destekleyen işletim sistemleri, rastgele 64 bit sanal adreslerini kullanarak yürütülebilir görüntünün segmentlerini yükleme zamanında yeniden temellendirebilirler. Bu büyük adres alanı, bir saldırganın belirli bir bellek bölgesinin konumunu tahmin etmesini zorlaştırır.

Varsayılan olarak, bağlayıcı **`/HIGHENTROPYVA`** 64 bitlik yürütülebilir görüntüler için etkinleştirilir. Bu seçenek hem hem de gerektirir [`/DYNAMICBASE`](dynamicbase.md) [`/LARGEADDRESSAWARE`](largeaddressaware.md) , bu da 64 bit görüntüler için varsayılan olarak etkindir. **`/HIGHENTROPYVA`** , seçeneğinin yoksayıldığı 32 bitlik yürütülebilir görüntüler için geçerli değildir. Bu seçeneği açıkça devre dışı bırakmak için kullanın **`/HIGHENTROPYVA:NO`** .

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)\
[`/DYNAMICBASE`](dynamicbase.md)\
[`/LARGEADDRESSAWARE`](largeaddressaware.md)\
[Windows ISV yazılım güvenliği savunmaları](/previous-versions/bb430720(v=msdn.10))
