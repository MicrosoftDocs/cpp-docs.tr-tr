---
title: -HIGHENTROPYVA | Microsoft Docs
ms.custom: ''
ms.date: 06/12/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /HIGHENTROPYVA
dev_langs:
- C++
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fec9314be9d69e2cb0af2a98884bd78de1ff679
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211652"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

Yürütülebilir resmin yüksek entropili 64-bit rastgele adres alanı düzenini (ASLR) destekleyip desteklemediğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ HIGHENTROPYVA**[**: NO**]

## <a name="remarks"></a>Açıklamalar

Bu seçenek üstbilgisi değiştirir bir *yürütülebilir görüntü*, bir .dll dosyasının veya .exe dosyası, 64 bit adresli aslr desteği olup olmadığını belirtmek için. Bu seçenek yürütülebilir olarak ve tüm bağımlı modüllerini ayarlandığında, 64 bit ASLR destekleyen bir işletim sistemi yürütülebilir resmin parçalarını yükleme zamanında bir 64 bit sanal adres alanında rastgele adresler kullanarak ReBase işlemi yapabilirsiniz. Bu geniş adres alanı bir saldırganın belirli bir bellek bölgesinin konumunu tahmin edilmesi daha zor hale getirir.

Bağlayıcı varsayılan olarak etkinleştirir **/highentropyva** 64-bit yürütülebilir resimler için. Bu seçenek gerektirir [/largeaddressaware](largeaddressaware.md), ayrıca etkin olan 64-bit görüntüleri için varsayılan olarak. **/ HIGHENTROPYVA** nerede seçenek göz ardı edilir 32-bit yürütülebilir resimler için geçerli değildir. Açıkça bu seçeneği devre dışı bırakma, **/HIGHENTROPYVA:NO**. Bu seçeneğin bir etkiye sahip olma [dynamıcbase](dynamicbase.md) seçeneği de ayarlanması gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [EDITBIN Seçenekleri](editbin-options.md)
- [/DYNAMICBASE](dynamicbase.md)
- [ISV yazılım güvenlik Savunmaları Windows](https://msdn.microsoft.com/library/bb430720.aspx)
