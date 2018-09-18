---
title: Kaynak Derleyicisi önemli hatası RC1015 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC1015
dev_langs:
- C++
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7a72cba53ebe9a286ac2e7cbbf2c41b78f4e4e08
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100772"
---
# <a name="resource-compiler-fatal-error-rc1015"></a>Kaynak Derleyicisi Önemli Hatası RC1015

'dosyaadı' dosyası açık içeremez

Verilen içerme dosyası mevcut değil, açılamadı veya bulunamadı.

Ortam ayarlarının geçerli olduğunu ve dosya için doğru yol belirtildiğinden emin olun. Kaynak derleyicisi için yeterli dosya tanıtıcısı kullanılabildiğinden emin olun. Dosya bir ağ sürücüsündeyse, dosyayı açmak için izinlere sahip olduğunuzdan emin olun.

Ek içeren dizin, yapılandırma özellikleri -> olarak kaynakları belirtilen bir dizinde içerme dosyası mevcut olsa bile RC1015 oluşabilir; genel özellik sayfası -> içerme dosyasının tam yolunu belirtin.

Bilgi Bankası makalesi Q326987 daha fazla bilgi için bkz: RC1015 hata olduğunda kullanarak kaynağın görünüm yoluna ise çok uzun.