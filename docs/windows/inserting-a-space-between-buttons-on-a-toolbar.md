---
title: (C++) araç çubuğundaki düğmeler arasına boşluk koyma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Toolbar editor [C++], spacing toolbar buttons
- toolbar buttons [C++], space between buttons
ms.assetid: 4925ea6b-5d3a-4949-a920-bf371a37e529
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 09086ea214bcf2abd9708f8abcee4f9f5f376994
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313422"
---
# <a name="inserting-a-space-between-buttons-on-a-toolbar-c"></a>(C++) araç çubuğundaki düğmeler arasına boşluk koyma

Genel olarak, düğmeler arasına boşluk eklemek için bunları birbirine uzağa araç sürüklemeniz yeterlidir. Alanı kaldırmak için bunları birbirine doğru sürükleyin.

### <a name="to-insert-a-space-before-a-button-that-is-not-followed-by-a-space"></a>Boşluk önce bir boşluk tarafından izlenmeyen bir düğme eklemek için

1. İleri düğmesine hakkında yarı yarıya çakışıyor kadar aşağı ya da sağ düğme sürükleyin.

### <a name="to-insert-a-space-before-a-button-which-is-followed-by-a-space-and-to-retain-that-trailing-space"></a>Ardından bir boşluk bir düğme öncesinde bir boşluk eklemek ve bu boşluk korumak için

1. Düğmeyi kadar sağa sürükleyin veya alt kenarı yalnızca İleri düğmesine oncollisionstay veya yalnızca çakışıyor.

### <a name="to-insert-a-space-before-a-button-that-is-followed-by-a-space-and-close-up-that-following-space"></a>Ardından bir boşluk bir düğme önce bir boşluk ekleyin ve aşağıdaki söz konusu alanı kapatmak için

1. İleri düğmesine hakkında yarı yarıya çakışıyor kadar aşağı ya da sağ düğme sürükleyin.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Araç Çubuğu Düğmelerini Oluşturma, Taşıma ve Düzenleme](../windows/creating-moving-and-editing-toolbar-buttons.md)  
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)