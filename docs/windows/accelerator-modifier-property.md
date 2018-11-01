---
title: Hızlandırıcı değiştirme özelliği (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
ms.openlocfilehash: f9dfcbde68d2b3d1ebdd1b94aa40339bbc0ff4e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650717"
---
# <a name="accelerator-modifier-property-c"></a>Hızlandırıcı değiştirme özelliği (C++)

Hızlandırıcı tablosunda değiştirici özelliği için yasal girdileri verilmiştir.

|Değer|Açıklama|
|-----------|-----------------|
|**Yok**|Kullanıcı yalnızca **anahtar** değeri. Bu en etkili bir şekilde 026 aracılığıyla 001 ASCII/ANSI değerleri olarak yorumlanıp kullanılır ^ A-^ Z (CTRL-CTRL-Z A).|
|**Alt**|Kullanıcı gerekir basın **Alt** önce anahtar **anahtar** değeri.|
|**CTRL**|Kullanıcı gerekir basın **Ctrl** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
|**Kaydırma**|Kullanıcı gerekir basın **Shift** önce anahtar **anahtar** değeri.|
|**Ctrl + Alt**|Kullanıcı gerekir basın **Ctrl** anahtarı ve **Alt** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
|**CTRL + üst karakter**|Kullanıcı gerekir basın **Ctrl** anahtarı ve **Shift** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
|**Alt + üst karakter**|Kullanıcı gerekir basın **Alt** anahtarı ve **Shift** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
|**Ctrl + Alt + üst karakter**|Kullanıcı gerekir basın **Ctrl**, **Alt**, ve **Shift** önce **anahtar** değeri. ASCII türü geçerli değil.|

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Özelliklerini Ayarlama](../windows/setting-accelerator-properties.md)<br/>
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)