---
title: Görüntüyü Yeniden Boyutlandırma (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.image.editing
helpviewer_keywords:
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
- size [C++], images
- images [C++], cropping
- images [C++], extending
- Image editor [C++], cropping or extending images
- Image editor [C++], shrinking and stretching images
- images [C++], stretching
- images [C++], shrinking
- bitmaps [C++], shrinking
- bitmaps [C++], stretching
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
ms.openlocfilehash: d88a4cccff5b9b7b6303329782b7367cb953b13d
ms.sourcegitcommit: 5270117dbecc4c49bca0cf10b927bae3c9930038
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55484974"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Görüntüyü Yeniden Boyutlandırma (Simgeler İçin Görüntü Düzenleyicisi)

Davranışını **görüntü** görüntüyü yeniden boyutlandırma sırasında Düzenleyicisi bağlı olup seçtiğiniz [seçili](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) görüntünün tamamını veya yalnızca bir bölümü.

Seçimi görüntüsü yalnızca bir bölümünü içerdiğinde **görüntü** Düzenleyicisi satırları veya sütunları piksel silme ve arka plan rengiyle boşaltılmış bölgeleri girerek seçim küçültür. Seçimi satır veya sütun piksel çoğaltarak ayrıca uzatabilirsiniz.

Seçimi görüntünün tamamını içerdiği durumlarda **görüntü** Düzenleyici ya da daraltır ve resmi uzatır veya kırpar ve genişletir.

Görüntüyü yeniden boyutlandırma için iki mekanizma vardır: boyutlandırma ve [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Görüntünün bir parçasını ve tüm boyutunu değiştirmek için boyutlandırma sürükleyin. Sürükleyebilirsiniz boyutlandırma tutamaçlarını dolu. Boş tanıtıcıları sürükleyemezsiniz. Kullanım **özellikleri** tamamını yeniden boyutlandırmak için pencere görüntü yalnızca seçili bir parçası değil.

![Boyutlandırma tutamaçları üzerinde bir bit eşlem](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")<br/>
Boyutlandırma

> [!NOTE]
> Varsa **döşeme Kılavuzu** seçeneğe [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md), ardından sonraki kutucuğu kılavuz çizgisi yapışır yeniden boyutlandırma. Yalnızca **piksel kılavuzunu** seçeneği (varsayılan ayar) seçili, sonraki kullanılabilir piksel yapışır yeniden boyutlandırma.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-resize-an-entire-image-using-the-properties-window"></a>Özellikler penceresini kullanarak görüntünün tümünü yeniden boyutlandırma

1. Özelliklerini değiştirmek istediğiniz görüntüyü açın.

1. İçinde **genişliği** ve **yükseklik** kutularındaki [Özellikler penceresi](/visualstudio/ide/reference/properties-window), istediğiniz boyutları yazın.

   Resmin boyutu genişletirseniz **görüntü** Düzenleyicisi resmi sağa, aşağı, veya her ikisi de genişletir ve yeni bölge geçerli arka plan rengi ile doldurur. Görüntü uzatılabilir değil.

   Resmin boyutu kısaltırsanız **görüntü** Düzenleyicisi sağ veya alt kenarı veya her ikisi de resmi kırpar.

   > [!NOTE]
   > Kullanabileceğiniz **genişliği** ve **yükseklik** kısmi bir seçim değil yeniden boyutlandırmak için tüm görüntü yalnızca yeniden boyutlandırmak için özellikleri.

## <a name="to-crop-or-extend-an-entire-image"></a>Görüntünün tümünü kırpma veya

1. Görüntünün tamamını seçin.

   Görüntünün seçili ve görüntünün tamamını seçmek istediğiniz herhangi bir geçerli seçim kenarlığı dış görüntü seçin.

1. Resim doğru boyutta olana kadar boyutlandırma tutamacı sürükleyin.

Normalde, **görüntü** Düzenleyicisi kırpar veya bir görüntü yeniden boyutlandırma tutamacı hareket ettirerek boyutlandırma sırasında genişletir. Basılı tutun, **Shift** anahtar bir boyutlandırma tutamacı hareket ettikçe **görüntü** Düzenleyicisi daraltır ya da resmi uzatır.

## <a name="to-shrink-or-stretch-an-entire-image"></a>Görüntünün Tümünü Genişlet veya Daralt

1. Görüntünün tamamını seçin.

   Görüntünün bir parçasını seçili ve görüntünün tamamını seçmek istediğiniz herhangi bir geçerli seçim kenarlığı dışındaki görüntüyü seçin.

1. Basılı **Shift** anahtar ve resim doğru boyutta olana kadar boyutlandırma tutamacı sürükleyin.

## <a name="to-shrink-or-stretch-part-of-an-image"></a>Küçültme veya uzatma bir görüntünün parçası

1. Görüntüyü yeniden boyutlandırmak istediğiniz bölümü seçin. Daha fazla bilgi için [görüntü alanını seçme](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md).

1. Boyutlandırma tutamaçlarından birinin doğru boyut seçimi olana kadar sürükleyin.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)