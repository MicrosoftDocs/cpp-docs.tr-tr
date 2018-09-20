---
title: Görüntü özelliklerini (simgeler için görüntü Düzenleyicisi) değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [C++], properties
- Image editor [C++], Properties window
- Properties window, image editor
ms.assetid: f6172bf1-08c4-4dfd-b542-dd8749e83fe6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3b85faff95e3053ea46edcedef7443cdab445d3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422239"
---
# <a name="changing-image-properties-image-editor-for-icons"></a>Görüntü Özelliklerini Değiştirme (Simgeler İçin Görüntü Düzenleyicisi)

Ayarlayabilir veya kullanmanın bir görüntü özelliklerini değiştirme [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

### <a name="to-change-an-images-properties"></a>Görüntünün özelliklerini değiştirmek için

1. Görüntüde açın **görüntü** Düzenleyici.

2. İçinde **özellikleri** penceresinde görüntünüzü tüm özelliklerini değiştirin.

   |Özellik|Açıklama|
   |--------------|-----------------|
   |**Renkler**|Görüntü için renk düzenini belirtir. Seçin **tek renkli**, **16**, veya **256**, veya **gerçek renk**. 16-renk paletini görüntüsüyle zaten şunu çizmişseniz, seçerek **tek renkli** değişimler siyah beyaz renkler için görüntüyü neden olur. Karşıtlık her zaman tutulmaz: Örneğin, kırmızı ve yeşil bitişik alanlarının her ikisini de siyah olarak dönüştürülür.|
   |**Dosya adı**|Görüntü dosyasının adını belirtir. Varsayılan olarak, Visual Studio varsayılan kaynak tanımlayıcısı (IDB_BITMAP1) ve uygun uzantısı ekleme ("IDB_") ilk dört karakterleri kaldırarak oluşturulan temel bir dosya adı atar. Bu örnekte bir görüntü için dosya adı `BITMAP1.bmp`. Bunu adlandırabilirsiniz `MYBITMAP1.bmp`.|
   |**Yükseklik**|Resmin yüksekliğini (piksel cinsinden) ayarlar. Varsayılan değer 48'dir. Resim kırpılmış veya mevcut görüntü altında boş bir boşluk eklenir.|
   |**ID**|Kaynağın tanımlayıcısını ayarlar. Bir görüntü için Microsoft Visual Studio, varsayılan olarak, serideki sonraki kullanılabilir tanımlayıcı atar: IDB_BITMAP1, IDB_BITMAP2, ve benzeri. Benzer adlar, simgeler ve İmleçler için kullanılır.|
   |**Palet**|Özellikleri rengi değiştirir. Bir renk seçin ve görüntülemek için çift [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Renk RGB veya HSL değerleri ilgili metin kutularına yazarak tanımlayın.|
   |**SaveCompressed**|Görüntü sıkıştırılmış bir biçimde olup olmadığını belirtir. Bu özellik salt okunurdur. Visual Studio izin vermemektedir görüntüleri sıkıştırılmış bir biçimde kaydetmek Visual Studio'da oluşturulan herhangi bir görüntü için bu özellik olacak şekilde **False**. (Başka bir programda oluşturan) bir sıkıştırılmış görüntüyü Visual Studio'da açarsanız, bu özellik olacak **True**. Visual Studio kullanarak bir sıkıştırılmış görüntüyü kaydederseniz, sıkıştırılmamış ve bu özellik, geri dönecek **False**.|
   |**Genişlik**|Resmin genişliğini (piksel cinsinden) ayarlar. 48 bit eşlemler için varsayılan değerdir. Resim kırpılmış veya boş alan var olan görüntünün sağına eklenir.|

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)