---
title: Depolama sınıfı tanımlayıcısı otomatik | Microsoft Docs
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
ms.openlocfilehash: 4054b723c1e44c94be9d112f6bfbd74db8f857ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381379"
---
# <a name="auto-storage-class-specifier"></a>auto Depolama Sınıfı Tanımlayıcısı
**Otomatik** depolama sınıfı tanımlayıcısı otomatik bir değişkeni, yerel bir ömre sahip bir değişken bildirir. Bir **otomatik** değişkenidir yalnızca bloğunda görünür, bildirildiği içinde. Bildirimlerini **otomatik** değişkenleri, başlatıcılar, içerebilir, anlatıldığı gibi [başlatma](../c-language/initialization.md). Değişkenlerle itibaren **otomatik** depolama sınıfı başlatılmadı otomatik olarak, bunları bildirme ya da deyimleri bloğu içinde ilk değerleri atamak, ya da açıkça bunları başlatması gerekir. Başlatılmamış değerlerini **otomatik** değişkenlerdir tanımlanmamış. (Bir yerel değişken **otomatik** veya **kaydetmek** depolama sınıfı, her seferinde onu gelirse kapsamında bir başlatıcı verilen başlatılır.)  
  
 Bir iç **statik** değişkeni (yerel statik değişkenle veya blok kapsamı) tüm dış adresiyle başlatılabilir veya **statik** öğesi, başka bir adres birlikte değil **otomatik**  , çünkü madde adresini bir **otomatik** öğe sabit bir değer değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto Anahtar Sözcüğü](../cpp/auto-keyword.md)