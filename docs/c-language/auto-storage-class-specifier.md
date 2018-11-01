---
title: auto Depolama Sınıfı Tanımlayıcısı
ms.date: 11/04/2016
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
ms.openlocfilehash: 926322fa55a14cc736dc41fbebd5c276ad61f020
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619914"
---
# <a name="auto-storage-class-specifier"></a>auto Depolama Sınıfı Tanımlayıcısı

**Otomatik** depolama sınıfı belirticisi, yerel kullanım ömrüne sahip bir değişken otomatik bir değişken bildirir. Bir **otomatik** değişkendir yalnızca blok içinde görülebilir içinde bildirildiği. Bildirimleri **otomatik** değişkenleri anlatıldığı gibi başlatıcılar içerebilir [başlatma](../c-language/initialization.md). Değişkenler **otomatik** depolama sınıfı otomatik olarak başlatılmadığından, bunları bildirdiğinizde veya içindeki blok içindeki deyimlerde başlangıç değerleri atamanız olduğunda, ya da açıkça bunları başlatmak. Başlatılmamış değerleri **otomatik** değişkenlerdir tanımlanmamış. (Bir yerel değişken **otomatik** veya **kaydetme** depolama sınıfı, her zaman bir başlatıcı verilirse kapsamda açıldığında başlatılır.)

Bir iç **statik** değişken (statik değişkeni yerel veya blok kapsamı) herhangi bir dış adresi ile başlatılabilir veya **statik** öğesi, ancak başka bir **otomatik**  , çünkü madde adresini bir **otomatik** öğesi bir sabit değil.

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../cpp/auto-keyword.md)