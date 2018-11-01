---
title: Hızlandırıcı türü özelliği (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Type property
- VIRTKEY
ms.assetid: 8c349bc4-e6ad-43fa-959e-f29168af35b8
ms.openlocfilehash: 00699f31b821aa508feec9ffe062d768f27ee5a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475597"
---
# <a name="accelerator-type-property-c"></a>Hızlandırıcı türü özelliği (C++)

Hızlandırıcı **türü** özelliği, Hızlandırıcı kimliği ile ilişkili kısayol tuş bileşimi bir sanal anahtar bileşimi veya ASCII/ANSI anahtar değeri olup olmadığını belirler:

- Varsa **türü** özelliğidir, ASCII [değiştiricisi](../windows/accelerator-modifier-property.md) yalnızca `None` veya `Alt`, veya kullanan bir Hızlandırıcı olabilir **Ctrl** (tarafından belirtilen anahtar anahtar ile önceki bir `^`).

- Varsa **türü** özelliktir VIRTKEY'e, herhangi bir birleşimini `Modifier` ve `Key` değerleri geçerlidir.

   > [!NOTE]
   > Hızlandırıcı tablosu içine bir değer girin ve ASCII/ANSI, yalnızca tıklatın değerlendirilmesi bir değere sahip istiyorsanız **türü** açılır listeden seçin ASCII ve tablo girişi. Ancak, kullanırsanız **sonraki anahtarı yazılan** komut (**Düzenle** menüsü) belirtmek için `Key`, değiştirmeniz gerekir **türü** VIRTKEY'e özelliğine ASCII *önce* girme `Key` kod.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Özelliklerini Ayarlama](../windows/setting-accelerator-properties.md)<br/>
[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)