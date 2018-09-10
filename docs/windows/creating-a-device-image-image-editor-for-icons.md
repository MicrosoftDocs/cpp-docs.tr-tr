---
title: Cihaz görüntüsü (simgeler için görüntü Düzenleyicisi) oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices [C++], creating image
- images [C++], creating for display devices
- icons [C++], inserting
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 753971a7b010c8e3af1c36c56833a123c182a708
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318128"
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>Cihaz Görüntüsü Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)

Yeni simgesi veya imleci kaynak oluşturduğunuzda **görüntü** Düzenleyicisi ilk oluşturur görüntü özel bir stili (32 x 32, 16 renk simgelerinin ve 32 x 32, tek renkli işaretçiler için). Ardından, ilk simgesi veya imleci için görüntüleri farklı boyut ve stil ekleyin ve ek her görüntü, farklı ekran cihazları için gerektiği gibi düzenleyin. Bir görüntü var olan bir görüntü türü veya bir grafik programında oluşturulan bir bit eşlem kesme ve yapıştırma işlemi gerçekleştirerek de düzenleyebilirsiniz.

Simgesi veya imleci kaynak açtığınızda [Resim Düzenleyicisi](../windows/image-editor-for-icons.md), görüntünün en yakın geçerli görüntü cihazı eşleşen varsayılan olarak açılır.

### <a name="to-create-a-new-icon-or-cursor"></a>Yeni simgesi veya imleci oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın ve ardından seçin **kaynak Ekle** kısayol menüsünden. (Bir imleç gibi bir .rc dosyasında var olan bir görüntü kaynağı zaten varsa, yalnızca sağ tıklayabilirsiniz **imleç** klasörü ve select **imleci yerleştirin** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md)seçin **simgesi** veya **imleç** tıklatıp **yeni**. Simgeler için bu bir 32 x 32 ile 16-renk simgesi bir simge kaynağı oluşturur. İmleçler, bir 32 x 32, tek renkli (2-color) görüntü oluşturulur.

   Bir artı işareti (**+**) görüntü kaynak türünü yanında **kaynak Ekle** iletişim kutusu, geldiğini araç şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin ve tıklayın artı işaretine tıklayın **yeni**.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)  
[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)  
[Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)