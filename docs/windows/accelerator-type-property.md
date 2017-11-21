---
title: "Hızlandırıcı türü özelliği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ef1788f451597cdc8d3b512f5eede3c3d5abb382
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="accelerator-type-property"></a>Hızlandırıcı Türü Özelliği
Hızlandırıcı **türü** özelliği Hızlandırıcı Kimliğiyle ilişkilendirilmiş kısayol tuş bileşimini sanal bir tuş bileşimini veya ASCII/ANSI anahtar değeri olup olmadığını belirler:  
  
-   Varsa **türü** özelliği **ASCII**, [değiştiricisi](../windows/accelerator-modifier-property.md) yalnızca hiçbiri olabilir veya Alt ya da CTRL tuşunu kullanan bir kısayol olabilir (anahtarla koyarak belirtilen bir ^).  
  
-   Varsa **türü** özelliği **VIRTKEY**, herhangi bir bileşimini değiştirici ve anahtar değerleri geçerlidir.  
  
    > [!NOTE]
    >  Hızlandırıcı tabloya bir değer girin ve ASCII/ANSI kabul değeri istiyorsanız, tablo girişi için türü ve açılır listeden seçin ASCII tıklamanız yeterlidir. Ancak, kullanırsanız **sonraki anahtar yazılan** komutu (**Düzenle** menüsü) anahtarını belirtmek için değiştirmeniz gerekir **türü** VIRTKEY özelliğine ASCII *önce* anahtar kodunu girerek.  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı özelliklerini ayarlama](../windows/setting-accelerator-properties.md)   
 [Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)