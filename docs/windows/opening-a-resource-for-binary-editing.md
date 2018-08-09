---
title: Kaynağı ikili düzenleme için açma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- resources [Visual Studio], opening for binary editing
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 26d1b0ae8923835b0ce06c7312fa185693c6586e
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014513"
---
# <a name="opening-a-resource-for-binary-editing"></a>Kaynağı İkili Düzenleme İçin Açma
### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>İkili düzenleme için bir Windows Masaüstü kaynağını açmak için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md), düzenlemek istediğiniz belirli bir kaynak dosyasını seçin.  
  
    > [!NOTE]
    >  Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Kaynak sağ tıklatıp **açık ikili veri** kısayol menüsünden.  
  
    > [!NOTE]
    >  Kullanırsanız [kaynak görünümü](../windows/resource-view-window.md) Visual Studio (RCDATA veya özel bir kaynak gibi), kaynak tanımıyor, biçimi ile bir kaynak penceresini açık otomatik olarak **ikili** Düzenleyici.  
  
### <a name="to-open-a-managed-resource-for-binary-editing"></a>İkili düzenleme için bir yönetilen kaynak açmak için  
  
1.  İçinde **Çözüm Gezgini**, düzenlemek istediğiniz belirli bir kaynak dosyasını seçin.  
  
2.  Kaynak sağ tıklatın ve seçin **birlikte Aç** kısayol menüsünden.  
  
3.  İçinde **birlikte Aç** iletişim kutusunda **ikili düzenleyici**.  
  
    > [!NOTE]
    >  Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.  
  
    > [!NOTE]
    >  Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).   
  
 ![İkili Düzenleyici](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")  
İkili veriler için ikili dosya Düzenleyicisi'nde görüntülenen iletişim kutusu  
  
 Yalnızca belirli ASCII değerleri (0x20 0x7E aracılığıyla) ikili düzenleyicide temsil edilir. Genişletilmiş karakterler, nokta İkili Düzenleyicisi (sağ panelde) ASCII değeri bölümünde görüntülenir. "Yazdırılabilir" karakterleri ASCII 32 126-değerlerdir.  
  
> [!NOTE]
>  Kullanmak istiyorsanız **ikili** zaten başka bir düzenleyici penceresinde düzenlenmekte olan bir kaynak düzenleyicisini diğer düzenleyici penceresini önce kapatın.  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili Düzenleyicisi](binary-editor.md)