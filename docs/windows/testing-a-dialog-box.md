---
title: Bir iletişim kutusu (C++) test etme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Test Dialog command
- testing, dialog boxes
- dialog boxes [C++], testing
ms.assetid: 45034ee9-c554-4f4b-8c46-6ddefdee8951
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ca5e8cfc2a08b01d7917d540c61e04837169a457
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438606"
---
# <a name="testing-a-dialog-box-c"></a>Test iletişim kutusu (C++)

Bir iletişim kutusu tasarlarken benzetimini gerçekleştirmek ve programınızı derlemeden çalışma zamanı davranışını sınama. Bu modda şunları yapabilirsiniz:

- Bir metin yazın, birleşik giriş kutusu listelerinden seçin, seçeneklerini açıp kapatabilir ve komutları seçin.

- Sekme sırasını test edin.

- Radyo düğmeleri ve onay kutuları gibi gruplandırmalarını test edin.

- İletişim kutusundaki denetimlerin klavye kısayollarını test.

   > [!NOTE]
   > Sihirbazları kullanarak yapılan iletişim kutusu kodu bağlantıları benzetime dahil edilmez.

Bir iletişim kutusunu test ettiğinizde, genellikle ana program penceresiyle ilişkili bir konumda görüntüler. İletişim kutusunun ayarladıysanız **mutlak hizalama** özelliğini **True**, ekranın sol üst köşesine göre olan konumda iletişim kutusunu görüntüler.

### <a name="to-test-a-dialog-box"></a>Bir iletişim kutusu test etmek için

1. Zaman **iletişim** Düzenleyicisi etkin pencere menü çubuğunda, seçin **biçimi** > **Test iletişim**.

2. Benzetimi bitirmek için basın **Esc**, veya yalnızca seçin **Kapat** test ettiğiniz iletişim kutusundaki düğmesi.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)<br/>
[İletişim Kutusu Araç Çubuğunu Gösterme veya Gizleme](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)