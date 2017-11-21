---
title: "Depolama sınıfı tanımlayıcısı otomatik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5e80f6057a26ba7655df0a04d75dcaec2c4856ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="auto-storage-class-specifier"></a>auto Depolama Sınıfı Tanımlayıcısı
**Otomatik** depolama sınıfı tanımlayıcısı otomatik bir değişkeni, yerel bir ömre sahip bir değişken bildirir. Bir **otomatik** değişkenidir yalnızca bloğunda görünür, bildirildiği içinde. Bildirimlerini **otomatik** değişkenleri, başlatıcılar, içerebilir, anlatıldığı gibi [başlatma](../c-language/initialization.md). Değişkenlerle itibaren **otomatik** depolama sınıfı başlatılmadı otomatik olarak, bunları bildirme ya da deyimleri bloğu içinde ilk değerleri atamak, ya da açıkça bunları başlatması gerekir. Başlatılmamış değerlerini **otomatik** değişkenlerdir tanımlanmamış. (Bir yerel değişken **otomatik** veya **kaydetmek** depolama sınıfı, her seferinde onu gelirse kapsamında bir başlatıcı verilen başlatılır.)  
  
 Bir iç **statik** değişkeni (yerel statik değişkenle veya blok kapsamı) tüm dış adresiyle başlatılabilir veya **statik** öğesi, başka bir adres birlikte değil **otomatik**  , çünkü madde adresini bir **otomatik** öğe sabit bir değer değil.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Auto anahtar sözcüğü](../cpp/auto-keyword.md)