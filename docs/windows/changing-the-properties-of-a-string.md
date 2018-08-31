---
title: Bir dizenin özelliklerini değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource identifiers, string properties
- string tables, changing strings
- strings [C++], properties
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5897801a0b0350d813f7dddc5d1595e04213e2dd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221646"
---
# <a name="changing-the-properties-of-a-string"></a>Dizenin Özelliklerini Değiştirme

### <a name="to-change-a-string-or-its-identifier"></a>Bir dize veya tanımlayıcısını değiştirmek için

1. Dize tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. Düzenle ve çift dize seçin **kimliği**, **değer**, veya **açıklamalı alt yazı** sütun. Artık şunları yapabilirsiniz:

   - Seçin bir **kimliği** gelen **kimliği açılan** liste veya türü bir `ID` doğrudan yerinde.

   - Farklı bir sayı yazın **değer** sütun.

   - Tür düzenlemeleri **açıklamalı alt yazı** sütun.

        > [!NOTE]
        >  Bir dizenin özelliklerini de düzenleyebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

Yönetilen projelere kaynak (Bu ortak dil çalışma zamanını hedefleyen) ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Dize Düzenleyicisi](../windows/string-editor.md)  