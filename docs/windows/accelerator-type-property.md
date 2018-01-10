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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 214d8ca9c45a3657215833764268794b152bd337
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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