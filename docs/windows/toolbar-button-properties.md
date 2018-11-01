---
title: Araç çubuğu düğmesi özellikleri (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
ms.openlocfilehash: f20556ac088180ceb1ed979c3e02ffc465b41c7b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665380"
---
# <a name="toolbar-button-properties-c"></a>Araç çubuğu düğmesi özellikleri (C++)

Araç çubuğu düğmesi özellikleri şunlardır:

|Özellik|Açıklama|
|--------------|-----------------|
|**ID**|Düğme için kimliği tanımlar. Açılır listede ortak sağlar **kimliği** adları.|
|**Genişlik**|Düğmesinin genişliğini belirler. 16 piksel önerilir.|
|**Yükseklik**|Düğmenin yüksekliğini belirler. Bir düğmenin yüksekliğini araç çubuğundaki tüm düğmeler yüksekliğini değiştiğine dikkat edin. 15 piksel önerilir.|
|**istemi**|Durum çubuğunda görüntülenen ileti tanımlar. Bir araç ipucu \n ve bir ad eklemek için bu araç çubuğu düğmesini ekler. Daha fazla bilgi için [bir araç ipucu oluşturmanın](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|

**Genişlik** ve **yükseklik** tüm düğmeler için geçerlidir. Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048 maksimum genişliği sahiptir. Bu nedenle düğme genişliği 512 ayarlarsanız, yalnızca dört düğme olabilir ve genişliği için 513 ayarlarsanız, yalnızca üç düğme olabilir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

MFC veya ATL

## <a name="see-also"></a>Ayrıca Bkz.

[Araç Çubuğu Düğmesi Özelliklerini Değiştirme](../windows/changing-the-properties-of-a-toolbar-button.md)<br/>
[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)