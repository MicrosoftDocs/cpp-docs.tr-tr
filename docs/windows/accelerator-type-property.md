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
ms.openlocfilehash: 59fae6d0809e32883d5d56e43e64525e23643d91
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602332"
---
# <a name="accelerator-type-property"></a>Hızlandırıcı Türü Özelliği

Hızlandırıcı **türü** özelliği, Hızlandırıcı kimliği ile ilişkili kısayol tuş bileşimi bir sanal anahtar bileşimi veya ASCII/ANSI anahtar değeri olup olmadığını belirler:

- Varsa **türü** özelliğidir, ASCII [değiştiricisi](../windows/accelerator-modifier-property.md) yalnızca `None` veya `Alt`, veya kullanan bir Hızlandırıcı olabilir **Ctrl** (tarafından belirtilen anahtar anahtar ile önceki bir `^`).

- Varsa **türü** özelliktir VIRTKEY'e, herhangi bir birleşimini `Modifier` ve `Key` değerleri geçerlidir.

   > [!NOTE]
   > Hızlandırıcı tablosu içine bir değer girin ve ASCII/ANSI, yalnızca tıklatın değerlendirilmesi bir değere sahip istiyorsanız **türü** açılır listeden seçin ASCII ve tablo girişi. Ancak, kullanırsanız **sonraki anahtarı yazılan** komut (**Düzenle** menüsü) belirtmek için `Key`, değiştirmeniz gerekir **türü** VIRTKEY'e özelliğine ASCII *önce* girme `Key` kod.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Özelliklerini Ayarlama](../windows/setting-accelerator-properties.md)  
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)