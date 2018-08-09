---
title: Hızlandırıcı türü özelliği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da825a4f2052f05b24ff724d709c7c8a4b6a3db3
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645691"
---
# <a name="accelerator-type-property"></a>Hızlandırıcı Türü Özelliği
Hızlandırıcı **türü** özelliği, Hızlandırıcı kimliği ile ilişkili kısayol tuş bileşimi bir sanal anahtar bileşimi veya ASCII/ANSI anahtar değeri olup olmadığını belirler:  
  
-   Varsa **türü** özelliğidir, ASCII [değiştiricisi](../windows/accelerator-modifier-property.md) yalnızca `None` veya `Alt`, veya kullanan bir Hızlandırıcı olabilir **Ctrl** (tarafından belirtilen anahtar anahtar ile önceki bir `^`).  
  
-   Varsa **türü** özelliktir VIRTKEY'e, herhangi bir birleşimini `Modifier` ve `Key` değerleri geçerlidir.  
  
    > [!NOTE]
    >  Hızlandırıcı tablosu içine bir değer girin ve ASCII/ANSI, yalnızca tıklatın değerlendirilmesi bir değere sahip istiyorsanız **türü** açılır listeden seçin ASCII ve tablo girişi. Ancak, kullanırsanız **sonraki anahtarı yazılan** komut (**Düzenle** menüsü) belirtmek için `Key`, değiştirmeniz gerekir **türü** VIRTKEY'e özelliğine ASCII *önce* girme `Key` kod.  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı özelliklerini ayarlama](../windows/setting-accelerator-properties.md)   
 [Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)