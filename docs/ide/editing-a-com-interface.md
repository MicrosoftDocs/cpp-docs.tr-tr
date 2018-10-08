---
title: COM arabirimini düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.com.editing.interfaces
dev_langs:
- C++
helpviewer_keywords:
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f660f9d69fc787384fcfbec37caec0064a58ec29
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861349"
---
# <a name="editing-a-com-interface"></a>COM Arabirimini Düzenleme

Sınıf Görünümü kısayol menüsünden komutlarını kullanarak, Visual C++ projelerine yeni yöntemleri ve özellikleri COM arabirimlerinin tanımlayabilirsiniz. Ayrıca, araç kutusundan ActiveX denetimleri için olayları tanımlayabilirsiniz.

ATL ve MFC tabanlı COM nesne sınıfları için sınıf uygulamasını arabirimi Düzen aynı zamanda düzenleyebilirsiniz.

> [!NOTE]
>  Dışında tanımlanan arabirimleri için **sınıfı Ekle** iletişim kutusunda, Visual C++ özellikleri ve yöntemleri .idl dosyasına ekler ve bile arabirimler el ile eklendiğinde yöntemlerini uygulayan sınıflar için saplamalar ekleyin.

Aşağıdaki üç sihirbazlar, var olan arabirimler özelleştirmenize yardımcı olur. Bunlar, sınıf görünümünden kullanılabilir:

|Sihirbazı|Proje türü|
|------------|------------------|
|[Özellik Ekleme Sihirbazı](../ide/names-add-property-wizard.md)|ATL destekleyen ATL veya MFC projeleri Özellik eklemek istediğiniz bir arabirime sağ tıklayın.<br /><br />Visual C++ proje türü algılar ve Özellik Ekleme Sihirbazı'nı seçenekleri uygun şekilde değiştirir:<br /><br />-Görüntü arabirimlerinde bulunan kullanılarak oluşturulan projeler için [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md), Özellik Ekleme Sihirbazı'nı çağrılırken, MFC'ye belirli seçenekler sunar.<br />-MFC ActiveX denetim arabirimleri için Özellik Ekleme Sihirbazı'nı stok yöntemleri ve sağladığı biçimde kullanmanız veya denetim için özelleştirme özellikleri listesini sağlar.<br />-Diğer tüm arabirimleri için ekleme özelliği sihirbazları çoğu durumlarda kullanışlı seçenekler sağlar.|
|[Yöntem Ekleme Sihirbazı](../ide/add-method-wizard.md)|ATL destekleyen ATL veya MFC projeleri Yöntem eklemek istediğiniz bir arabirime sağ tıklayın.<br /><br />Visual C++ proje türü algılar ve buna uygun şekilde yöntem Ekleme Sihirbazı'nı seçenekleri değiştirir:<br /><br />-Görüntü arabirimlerinde bulunan kullanılarak oluşturulan projeler için [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md), yöntem Ekleme Sihirbazı'nı çağrılırken, MFC'ye belirli seçenekler sunar.<br />-MFC ActiveX denetim arabirimleri için yöntem Ekleme Sihirbazı'nı stok yöntemleri ve sağladığı biçimde kullanmanız veya denetim için özelleştirme özellikleri listesini sağlar.<br />-Diğer tüm arabirimler için **Ekle yöntemi** sihirbazlar çoğu durumlarda kullanışlı seçenekler sağlar.|

Ayrıca, nesnenin denetim sınıf Sınıf Görünümü'nde sağ tıklatıp COM denetiminizi yeni arabirim uygulayabilir [arabirimi uygulayan](../ide/implement-interface-wizard.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br>
[Kod sihirbazlarıyla işlevsellik ekleme](../ide/adding-functionality-with-code-wizards-cpp.md)<br>
[Visual C++ Proje Türleri](../ide/visual-cpp-project-types.md)