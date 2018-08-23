---
title: Denetimleri seçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, selecting controls
- dominant controls
- dialog box controls, selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 29372cc451105de81fc340da1e4e0de427551529
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595167"
---
# <a name="selecting-controls"></a>Denetimleri Seçme

Boyuta denetimleri seçin, hizalama, taşıyın, kopyalayın, veya silin ve sonra istediğiniz işlemi gerçekleştirin. Çoğu durumda, boyutu ve hizalama araçları kullanmak üzere birden fazla denetim seçmeniz gerekir [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Bir denetim seçili durumdayken, etrafında gölgeli bir kenarlık kesintisiz (etkin) sahip veya boş (etkin olmayan) "boyutlandırma tutamaçlarını" küçük kareler, zaman içinde seçim kenarlığı görüntülenir. Birden çok Denetim seçildiğinde, baskın denetimi düz boyutlandırma tutamaçlarını sahiptir; diğer seçilen tüm denetimleri boş boyutlandırma tutamaçlarını vardır.

Boyutlandırma veya birden çok denetimi hizalama **iletişim** Düzenleyicisi kullanır "baskın denetimi" diğer denetimlerin nasıl boyutlandırılmış veya hizalı belirlemek için. Varsayılan olarak, baskın denetim seçili ilk bir denetimdir.

- [Birden Çok Denetim Seçme](../windows/selecting-multiple-controls.md)

- [Baskın Denetimi Belirtme](../windows/specifying-the-dominant-control.md)

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)  
[Denetimler](../mfc/controls-mfc.md)