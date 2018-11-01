---
title: MFC Uygulamalarında Menü Komutlarını Durum Çubuğu Metniyle İlişkilendirme
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [C++], associating menu items
- menus [C++], status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
ms.openlocfilehash: fc39695358a9c1f2f62878487a5e4fedf5db2b82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468893"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>MFC Uygulamalarında Menü Komutlarını Durum Çubuğu Metniyle İlişkilendirme

MFC uygulamanızı her bir kullanıcı seçebilir menü komutları için açıklayıcı metni görüntüleyebilirsiniz. Bir metin dizesi kullanarak her menü komut atayarak bunu **istemi** özelliğinde **özellikleri** penceresi. Bir dize varsa [dize tablosu](../windows/string-editor.md) Kimliğine komutu ile aynıdır, bir kullanıcı bir menü öğesi geldiğinde bir MFC uygulaması otomatik olarak bu dize kaynağı çalışan uygulama durum çubuğunda görüntülenir.

### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>Bir menü komutu bir durum çubuğunda metin dizesi ile ilişkilendirmek için

1. İçinde **menü** Düzenleyicisi, menü komutunu seçin.

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ilgili durum çubuğu metni yazın **istemi** kutusu.

## <a name="requirements"></a>Gereksinimler

MFC

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Menüye Komut Ekleme](../windows/adding-commands-to-a-menu.md)<br/>
[Menü Düzenleyicisi](../windows/menu-editor.md)