---
title: Saydam veya donuk arka plan (simgeler için görüntü Düzenleyicisi) seçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- opaque backgrounds
- background colors, images
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- background images
- images [C++], transparency
- images [C++], opaque background
- transparent backgrounds
- transparency, background
- transparent backgrounds, images
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 244e6a63bc16b5e83bb8419dbe1b53741d566e56
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857918"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>Saydam veya Donuk Arka Plan Seçme (Simgeler İçin Görüntü Düzenleyicisi)
Taşıdığınızda veya bir görüntüden Seçimi kopyalama geçerli arka plan rengi eşleşen tüm seçimi, varsayılan olarak, saydam pikseldir; Hedef konumda piksel soyutlamaması değil.  
  
 Saydam arka plan (varsayılan) donuk arka plana geçin ve yeniden. Bir seçim aracını kullandığınızda **saydam arka plan** ve **donuk arka plan** seçenekleri görünmez seçeneği seçicide **görüntü Düzenleyicisi** (aşağıda görüldüğü gibi) araç.  
  
 ![Arka plan seçenekleri &#45; donuk veya saydam](../windows/media/vcimageeditoropaqtranspback.gif "vcImageEditorOpaqTranspBack")  
Görüntü Düzenleyicisi araç çubuğundaki saydam ve donuk seçenekleri  
  
### <a name="to-switch-between-a-transparent-and-opaque-background"></a>Saydam ve donuk arka plan arasında geçiş yapmak için  
  
1.  İçinde **görüntü Düzenleyicisi** araç tıklatın **seçeneği** Seçici ve ardından uygun arka plan:  
  
    -   **Donuk arka plan (O)**: Mevcut görüntü seçimi tüm bölümleri tarafından getirilmemeli.  
  
    -   **Saydam arka plan (T)**: Mevcut görüntü geçerli arka plan rengini eşleştirme seçimi bölümlerini gösterir.  
  
 \- veya -  
  
-   Üzerinde **görüntü** menüsünde seçin veya temizleyin **Donuk Çiz**.  
  
 Bir seçim hangi bölümlerinin resminin saydam değiştirmek için etkin durumdayken, arka plan rengini değiştirebilirsiniz.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)