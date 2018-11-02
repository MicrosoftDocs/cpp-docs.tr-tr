---
title: Anımsatıcıları Tanımlama (Erişim Tuşları)
ms.date: 11/04/2016
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls [C++], mnemonics
- access keys [C++], checking
- mnemonics [C++], checking for duplicate
- mnemonics
- mnemonics [C++], dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
ms.openlocfilehash: 8682ab38abebe1c453ef562e8eaac0e627f5c4bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488926"
---
# <a name="defining-mnemonics-access-keys"></a>Anımsatıcıları Tanımlama (Erişim Tuşları)

Normalde, klavye kullanıcıları içeren bir iletişim kutusu alanındaki başka bir denetimden giriş odağı Taşı **sekmesini** ve **ok** anahtarları. Ancak, tek bir tuşa basarak bir denetim seçmelerini sağlar bir erişim anahtarı (bir anımsatıcı ya da unutmayacağınızdan kolay ad) tanımlayabilirsiniz.

### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Bir denetimin görünür başlığı (düğmeler, onay kutularını ve radyo düğmeleri) olan bir erişim tuşunu tanımlamak için

1. İletişim kutusunda bir denetimi seçin.

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), **açıklamalı alt yazı** özelliği, ve işareti yazarak denetim için yeni bir ad yazın (`&`) Bu denetim için erişim anahtarı olarak istediğiniz harfi önünde. Örneğin: `&Radio1`

3. Tuşuna **girin**.

   Örneğin, erişim anahtarı belirtmek için görüntülenen resim bir çizgi görünür **R**adio1.

### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Resim yazısı görünür olmayan bir denetim için bir erişim tuşunu tanımlamak için

1. Denetim için bir başlık kullanarak yapmak bir **statik metin** denetim [araç kutusu](/visualstudio/ide/reference/toolbox).

2. Statik metin başlığı ve işareti yazın (`&`) erişim anahtarı olarak istediğiniz harfi önünde.

3. Statik metin denetimi sekme sırasının etiket denetimi karaktere emin olun.

Bir iletişim kutusu içindeki tüm erişim anahtarları benzersiz olmalıdır.

### <a name="to-check-for-duplicate-access-keys"></a>Yinelenen erişim tuşları denetlemek için

1. Üzerinde **biçimi** menüsünde tıklatın **anımsatıcıları kontrol**.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)