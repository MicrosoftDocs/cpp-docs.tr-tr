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
ms.openlocfilehash: b2ff9929de74d99fbc45e4f4ff38fd6b939697bc
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373833"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Yürütülebilir resmin yüksek entrolebilir 64 bit adres alanı düzeni rastgele seçimini (ASLR) destekleyip desteklemediğini belirtir.

## <a name="syntax"></a>Syntax

> **/highentropyva**[**: No**]

## <a name="remarks"></a>Açıklamalar

Bu seçenek, 64 bitlik adresler içeren ASLR 'in desteklenip desteklenmediğini göstermek için bir. dll dosyası veya. exe dosyası olan *yürütülebilir bir görüntünün*üst bilgisini değiştirir. Bu seçenek, bir yürütülebilir dosya ve bağımlı olduğu tüm modüller üzerinde ayarlandığında, 64 bitlik ASLR destekleyen bir işletim sistemi, bir 64 bit sanal adres alanında rastgele adresler kullanarak, yükleme zamanında yürütülebilir görüntünün segmentlerini yeniden temellendirebilirler. Bu büyük adres alanı, bir saldırganın belirli bir bellek bölgesinin konumunu tahmin etmesini zorlaştırır.

Varsayılan olarak, bağlayıcı 64 bitlik yürütülebilir görüntüler için **/highentropyva** 'yı mümkün bir şekilde sunar. Bu seçenek, 64 bit görüntüler için varsayılan olarak da etkinleştirilen [/LARGEADDRESSAWARE](largeaddressaware.md)gerektirir. **/Highentropyva** , seçeneğin yoksayıldığı 32 bitlik yürütülebilir görüntüler için geçerli değildir. Bu seçeneği açıkça devre dışı bırakmak için **/highentropyva: No**komutunu kullanın. Bu seçeneğin bir etkisi olması için [/DynamicBase](dynamicbase.md) seçeneğinin de ayarlanmış olması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [EDITBIN seçenekleri](editbin-options.md)
- [/DYNAMICBASE](dynamicbase.md)
- [Windows ISV yazılım güvenliği savunmaları](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
