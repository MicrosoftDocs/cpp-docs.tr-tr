---
description: Daha fazla bilgi edinin:/HIGHENTROPYVA
title: /HIGHENTROPYVA
ms.date: 06/12/2018
f1_keywords:
- /HIGHENTROPYVA
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
ms.openlocfilehash: ae7851bb9160601ef8732120dca12132dbfdee2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200045"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Yürütülebilir resmin yüksek entrolebilir 64 bit adres alanı düzeni rastgele seçimini (ASLR) destekleyip desteklemediğini belirtir.

## <a name="syntax"></a>Syntax

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>Açıklamalar

Bu seçenek  *`.dll`* *`.exe`* , 64 bitlik adres ASLR desteğini göstermek için yürütülebilir bir görüntü dosyasının (örneğin, bir veya dosyanın) üst bilgisini değiştirir. Bir etkiye sahip olmak için, hem çalıştırılabilir hem de bağımlı olduğu tüm modüller üzerinde seçeneğini ayarlayın. Ardından 64-bit ASLR destekleyen işletim sistemleri, rastgele 64 bit sanal adreslerini kullanarak yürütülebilir görüntünün segmentlerini yükleme zamanında yeniden temellendirebilirler. Bu büyük adres alanı, bir saldırganın belirli bir bellek bölgesinin konumunu tahmin etmesini zorlaştırır.

Varsayılan olarak, bağlayıcı **`/HIGHENTROPYVA`** 64 bitlik yürütülebilir görüntüler için etkinleştirilir. Bu seçenek hem hem de gerektirir [`/DYNAMICBASE`](dynamicbase.md) [`/LARGEADDRESSAWARE`](largeaddressaware.md) , bu da 64 bit görüntüler için varsayılan olarak etkindir. **`/HIGHENTROPYVA`** , seçeneğinin yoksayıldığı 32 bitlik yürütülebilir görüntüler için geçerli değildir. Bu seçeneği açıkça devre dışı bırakmak için kullanın **`/HIGHENTROPYVA:NO`** .

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)\
[`/DYNAMICBASE`](dynamicbase.md)\
[`/LARGEADDRESSAWARE`](largeaddressaware.md)\
[Windows ISV yazılım güvenliği savunmaları](/previous-versions/bb430720(v=msdn.10))
