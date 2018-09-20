---
title: Tek denetimleri boyutlandırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9932b14b3d3afaa0afdff90c08ce44bf1f8648dc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373487"
---
# <a name="sizing-individual-controls"></a>Tek Denetimleri Boyutlandırma

Bir denetimi yeniden boyutlandırmak için boyutlandırma tutamaçlarını kullanın. İşaretçi boyutlandırma tutamacı konumlandırıldığında Şekil Denetimi boyutlandırılabilir yönergeleri belirtmek için değiştirir. Etkin boyutlandırma tutamaçlarını düz; boyutlandırma tutamacı boş ise, bu eksen boyunca denetimi yeniden boyutlandırılamaz.

Denetim kılavuzları veya kenar boşlukları yaslama tarafından bir denetimin boyutunu değiştirebilirsiniz ya da taşıyarak bir denetim ve başka bir kılavuzu yaslanan.

### <a name="to-size-a-control"></a>Bir denetimi boyutlandırmak için

1. Denetimi seçin.

2. Denetimin boyutunu değiştirmek için boyutlandırma tutamaçlarını sürükleyerek:

   - Boyutlandırma üstünde ve kenarlar, yatay veya dikey boyutunu değiştirin.

   - Boyutlandırma köşelere yatay ve dikey boyutunu değiştirin.

   > [!TIP]
   > Basılı tutarak bir kerede denetimi bir iletişim birim (DLU) boyutlandırabilirsiniz **Shift** anahtar ve kullanarak **sağ ok** ve **aşağı ok** anahtarları.

### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Denetim içindeki metnin sığması için otomatik olarak boyutlandırmak için

1. Seçin **içerik boyutu** gelen **biçimi** menüsü.

\- veya -

- Denetime sağ tıklayın ve seçin **içerik boyutu** kısayol menüsünden.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)