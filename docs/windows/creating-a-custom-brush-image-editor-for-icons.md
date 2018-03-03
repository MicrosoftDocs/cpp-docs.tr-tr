---
title: "Özel fırça (simgeler için görüntü Düzenleyicisi) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38f376053635708372c09a37aa0810e4305db60a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>Özel Fırça Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)
Özel fırça almak ve bir görüntü Düzenleyicisi'nin hazır fırçalar gibi kullanan bir görüntü dikdörtgen bölümüdür. Bir seçimde gerçekleştirebileceğiniz tüm işlemler bir özel fırça üzerinde gerçekleştirebilirsiniz.  
  
### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Özel fırça bir kısmına bir görüntü oluşturmak için  
  
1.  [Görüntünün seçin](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) fırça için kullanmak istediğiniz.  
  
2.  Bulunduran **SHIFT** aşağı anahtar, seçim tıklatın ve görüntü boyunca sürükleyin.  
  
     \-veya -  
  
3.  Gelen **görüntü** menüsünde seçin **fırça olarak seçimini kullan**.  
  
     Seçimdeki renkleri görüntü boyunca dağıtan özel fırça seçiminizi olur. Seçimi kopyalarını sürükleme yol boyunca bırakılır. Daha yavaş sürüklediğiniz, o kadar fazla kopya yapılır.  
  
     **Not** tıkladığınızda **fırça olarak seçimi kullan** olmadan önce görüntünün bir kısmını seçerek görüntünün tamamını fırça olarak kullanır. Özel fırça kullanmanın sonucu olup olmadığını seçtiğiniz üzerinde de bağlıdır bir [donuk veya saydam arka plan](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
 Geçerli arka plan rengi eşleşen özel fırça pikseldir normalde saydam: Mevcut görüntü boyamak değil. Mevcut görüntü arka plan rengi piksel boyamak bu davranışı değiştirebilirsiniz.  
  
 Özel fırça damga veya bir şablon gibi çeşitli özel efektler oluşturmak için kullanabilirsiniz.  
  
#### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Arka plan rengi özel fırça şekiller çizmek için  
  
1.  [Saydam veya donuk arka plan seçme](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
2.  [Arka plan rengini ayarlama](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) istediğiniz çizmek rengi.  
  
3.  Özel fırça çizmek istediğiniz yere getirin.  
  
4.  Farenin sağ düğmesiyle tıklayın. Özel fırça donuk tüm bölümlerinin arka plan rengi çizilir.  
  
#### <a name="to-double-or-halve-the-custom-brush-size"></a>Çift veya özel fırça boyutu edilmesiyle yarıya  
  
1.  Tuşuna **artı** (**+**) fırça boyutu iki katına anahtar veya **eksi** (**-**) onu edilmesiyle yarıya anahtarı .  
  
#### <a name="to-cancel-the-custom-brush"></a>Özel fırça iptal etmek için  
  
1.  Tuşuna **ESC** veya başka bir çizim aracı seçin.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

