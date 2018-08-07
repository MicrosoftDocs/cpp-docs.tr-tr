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
ms.openlocfilehash: 428c62db8f1444f497d6fede7affea34560b4b0e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605961"
---
# <a name="opening-a-resource-for-binary-editing"></a>Kaynağı İkili Düzenleme İçin Açma
### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>İkili düzenleme için bir Windows Masaüstü kaynağını açmak için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md), düzenlemek istediğiniz belirli bir kaynak dosyasını seçin.  
  
    > [!NOTE]
    >  Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Kaynak sağ tıklatıp **açık ikili veri** kısayol menüsünden.  
  
    > [!NOTE]
    >  Kullanırsanız [kaynak görünümü](../windows/resource-view-window.md) penceresini Visual Studio (RCDATA veya özel bir kaynak gibi), kaynak tanımıyor, biçimiyle bir kaynağı otomatik olarak ikili düzenleyicide açılır.  
  
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
>  İkili Düzenleyici zaten başka bir düzenleyici penceresinde düzenlenmekte olan kaynak kullanmak istiyorsanız, diğer düzenleyici penceresini kapatın.  
  
## <a name="requirements"></a>Gereksinimler  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili Düzenleyicisi](binary-editor.md)