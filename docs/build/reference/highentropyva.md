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
ms.openlocfilehash: 1adc12c0673764460b4af5eb7cf3b394d9666e81
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404106"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Yürütülebilir resmin yüksek entrolebilir 64 bit adres alanı düzeni rastgele seçimini (ASLR) destekleyip desteklemediğini belirtir.

## <a name="syntax"></a>Syntax

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>Açıklamalar

Bu seçenek *executable image* *`.dll`* *`.exe`* , 64 bitlik adres ASLR desteğini göstermek için yürütülebilir bir görüntü dosyasının (örneğin, bir veya dosyanın) üst bilgisini değiştirir. Bir etkiye sahip olmak için, hem çalıştırılabilir hem de bağımlı olduğu tüm modüller üzerinde seçeneğini ayarlayın. Ardından 64-bit ASLR destekleyen işletim sistemleri, rastgele 64 bit sanal adreslerini kullanarak yürütülebilir görüntünün segmentlerini yükleme zamanında yeniden temellendirebilirler. Bu büyük adres alanı, bir saldırganın belirli bir bellek bölgesinin konumunu tahmin etmesini zorlaştırır.

Varsayılan olarak, bağlayıcı **`/HIGHENTROPYVA`** 64 bitlik yürütülebilir görüntüler için etkinleştirilir. Bu seçenek hem hem de gerektirir [`/DYNAMICBASE`](dynamicbase.md) [`/LARGEADDRESSAWARE`](largeaddressaware.md) , bu da 64 bit görüntüler için varsayılan olarak etkindir. **`/HIGHENTROPYVA`**, seçeneğinin yoksayıldığı 32 bitlik yürütülebilir görüntüler için geçerli değildir. Bu seçeneği açıkça devre dışı bırakmak için kullanın **`/HIGHENTROPYVA:NO`** .

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)\
[`/DYNAMICBASE`](dynamicbase.md)\
[`/LARGEADDRESSAWARE`](largeaddressaware.md)\
[Windows ISV yazılım güvenliği savunmaları](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
