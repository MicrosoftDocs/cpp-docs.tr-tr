---
title: Durum çubuğu metniyle MFC uygulamalarında menü komutlarını ilişkilendirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- status bars [C++], associating menu items
- menus [C++], status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 16de276478485cb52b11b3f1bbb869c5b75d05a4
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316763"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>MFC Uygulamalarında Menü Komutlarını Durum Çubuğu Metniyle İlişkilendirme

MFC uygulamanızı her bir kullanıcı seçebilir menü komutları için açıklayıcı metni görüntüleyebilirsiniz. Bir metin dizesi kullanarak her menü komut atayarak bunu **istemi** özelliğinde **özellikleri** penceresi. Bir dize varsa [dize tablosu](../windows/string-editor.md) Kimliğine komutu ile aynıdır, bir kullanıcı bir menü öğesi geldiğinde bir MFC uygulaması otomatik olarak bu dize kaynağı çalışan uygulama durum çubuğunda görüntülenir.

### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>Bir menü komutu bir durum çubuğunda metin dizesi ile ilişkilendirmek için

1. İçinde **menü** Düzenleyicisi, menü komutunu seçin.

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ilgili durum çubuğu metni yazın **istemi** kutusu.

## <a name="requirements"></a>Gereksinimler

MFC

## <a name="see-also"></a>Ayrıca Bkz.

[Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[Menüye Komut Ekleme](../windows/adding-commands-to-a-menu.md)  
[Menü Düzenleyicisi](../windows/menu-editor.md)