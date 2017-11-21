---
title: "Görüntü özelliklerini (simgeler için görüntü Düzenleyicisi) değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- images [C++], properties
- Image editor [C++], Properties window
- Image editor [C++], image properties
- Properties window, image editor
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f7320d385976ecc401decb8551b420fe8b210b04
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="changing-image-properties-image-editor-for-icons"></a>Görüntü Özelliklerini Değiştirme (Simgeler İçin Görüntü Düzenleyicisi)
Atama veya kullanarak bir görüntü özelliklerini değiştirme [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
### <a name="to-change-an-images-properties"></a>Görüntünün özelliklerini değiştirmek için  
  
1.  Görüntüde açın **görüntü** Düzenleyici.  
  
2.  İçinde **özellikleri** penceresinde görüntünüzü tüm özelliklerini değiştirin.  
  
    |Özellik|Açıklama|  
    |--------------|-----------------|  
    |**Renkleri**|Görüntü renk düzenini belirtir. Tek renkli, 16, 256 ya da doğru rengi seçin. Bir 16-renk paletini görüntüsüyle zaten çizilmiş değilse, tek renkli belirlenmesi siyah beyaz renkler için değişimler görüntüde neden olur. Karşıtlık her zaman tutulmaz: Örneğin, kırmızı ve yeşil bitişik alanlarının her ikisi de siyah dönüştürülür.|  
    |**Dosya adı**|Görüntü dosyasının adını belirtir. Varsayılan olarak, Visual Studio varsayılan kaynak tanımlayıcısı (IDB_BITMAP1) ve uygun uzantıyı eklemeden önce dört karakter ("IDB_") kaldırarak oluşturulan temel bir dosya adı atar. Bu örnekte görüntüsü için dosya adı BITMAP1.bmp olacaktır. MYBITMAP1.bmp adlandırabilirsiniz.|  
    |**Yükseklik**|Resmin yüksekliğini (piksel cinsinden) ayarlar. 48 varsayılan değerdir. Resim kırpılmış veya boşluk mevcut görüntü eklenir.|  
    |**KİMLİĞİ**|Kaynağın tanımlayıcı ayarlar. Bir görüntü için Microsoft Visual Studio, varsayılan olarak, bir serideki sonraki kullanılabilir tanımlayıcı atar: IDB_BITMAP1, IDB_BITMAP2, vb.. Benzer adlar, simgeler ve İmleçler için kullanılır.|  
    |**Palet**|Değişiklikleri özellikleri rengi. Bir renk seçin ve görüntülemek için çift [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Uygun kutulara RGB veya HSL değerleri yazarak rengi tanımlar.|  
    |**SaveCompressed**|Görüntü sıkıştırılmış biçimde olup olmadığını gösterir. Bu özellik salt okunurdur. Visual Studio izin vermez görüntüler sıkıştırılmış bir biçimde kaydetmek Visual Studio'da oluşturulan tüm görüntüleri için bu özellik olacak şekilde **False**. Visual Studio'da (başka bir programda oluşturulan) sıkıştırılmış görüntü açarsanız, bu özellik olacak **doğru**. Visual Studio kullanarak sıkıştırılmış bir görüntü kaydederseniz, sıkıştırılmamış ve bu özellik geri döner **False**.|  
    |**Genişlik**|Resmin genişliğini (piksel cinsinden) ayarlar. 48 bit eşlemler için varsayılan değerdir. Resim kırpılmış veya boşluk mevcut görüntü sağındaki eklenir.|  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

