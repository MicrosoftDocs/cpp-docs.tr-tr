---
title: İletişim kutusu (C++) denetimleri ile kod arasında geçiş yapma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- events [C++], viewing for controls
- Windows messages [C++], controls
- messages [C++], viewing for dialog boxes
- Dialog Editor [C++], accessing code
- code [C++], switching from Dialog Editor
- controls [C++], jumping to code
- Dialog Editor [C++], switching between controls and code
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ef2bcd7dc6bf70f4d0486334d71bd5f7798c83f
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314397"
---
# <a name="switching-between-dialog-box-c-controls-and-code"></a>İletişim kutusu (C++) denetimleri ile kod arasında geçiş yapma

MFC uygulamalarında iletişim kutusu denetimleri üzerinde işleyici kodlarını atlayın veya hızlı bir şekilde saplama işleyici işlevleri oluşturmak için çift tıklayabilirsiniz.

Bir denetim seçili durumdayken tıklayın **ControlEvents'i** düğmesini veya **iletileri** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window) Windows iletileri ve olayları tam listesini görüntülemek için Seçili öğe için kullanılabilir. Oluşturma veya düzenleme işleyici işlevleri listeden seçin.

### <a name="to-jump-to-code-from-the-dialog-editor"></a>İletişim kutusu düzenleyicisinden koda gitmek için

1. Bir denetim, en son uygulanan ileti işleme işlevinin bildirimi atlamak için iletişim kutusuna çift tıklayın. (İletişim ATL tabanlı sınıflar için her zaman Oluşturucusu tanımına atlayın.)

### <a name="to-view-events-for-a-control"></a>Bir denetim olaylarını görüntülemek için

1. Bir denetim seçili durumdayken tıklayın **ControlEvents'i** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

   > [!NOTE]
   > Tıklayarak **ControlEvents'i** olduğunda düğme *iletişim kutusu* odak kullanıma sunan sonra olayları tek tek denetimler için Düzen genişletebilirsiniz iletişim kutusunda, tüm denetimleri listesi vardır.

   Tek bir denetim, iletişim kutusunda odağa sahip olduğunda, sağ tıklatın ve seçin **olay işleyici Ekle** kısayol menüsünden. Bu sınıfı işleyici ekleneceği belirtmenize olanak sağlar. Daha fazla bilgi için [olay işleyici ekleme](../ide/adding-an-event-handler-visual-cpp.md).

### <a name="to-view-messages-for-a-dialog-box"></a>Bir iletişim kutusu iletilerini görüntülemek için

1. İletişim kutusu seçili tıklatın **iletileri** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)