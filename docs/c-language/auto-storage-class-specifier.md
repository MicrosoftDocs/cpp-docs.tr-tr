---
title: auto depolama sınıfı tanımlayıcısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca42eb26cc6bb08cd8a05e31b23e004b1cbeb8b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057437"
---
# <a name="auto-storage-class-specifier"></a>auto Depolama Sınıfı Tanımlayıcısı

**Otomatik** depolama sınıfı belirticisi, yerel kullanım ömrüne sahip bir değişken otomatik bir değişken bildirir. Bir **otomatik** değişkendir yalnızca blok içinde görülebilir içinde bildirildiği. Bildirimleri **otomatik** değişkenleri anlatıldığı gibi başlatıcılar içerebilir [başlatma](../c-language/initialization.md). Değişkenler **otomatik** depolama sınıfı otomatik olarak başlatılmadığından, bunları bildirdiğinizde veya içindeki blok içindeki deyimlerde başlangıç değerleri atamanız olduğunda, ya da açıkça bunları başlatmak. Başlatılmamış değerleri **otomatik** değişkenlerdir tanımlanmamış. (Bir yerel değişken **otomatik** veya **kaydetme** depolama sınıfı, her zaman bir başlatıcı verilirse kapsamda açıldığında başlatılır.)

Bir iç **statik** değişken (statik değişkeni yerel veya blok kapsamı) herhangi bir dış adresi ile başlatılabilir veya **statik** öğesi, ancak başka bir **otomatik**  , çünkü madde adresini bir **otomatik** öğesi bir sabit değil.

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../cpp/auto-keyword.md)