---
title: Kaynakları, kaynak düzenleyicisinde görüntüleme ve düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resourceview
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- rc files, viewing resources
- Resource View pane
- layouts, previewing resource
- code, viewing resources
- resource editors, viewing resources
- .rc files, viewing resources
- resources [Visual Studio], editing
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5fca755c46d3fc5628adc2c724b9307a346d1fe7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014009"
---
# <a name="viewing-and-editing-resources-in-a-resource-editor"></a>Kaynakları, Kaynak Düzenleyicisinde Görüntüleme ve Düzenleme
Her kaynak türüne sahip bir **kaynak** bu kaynak türü için belirli bir düzenleyici. Yeniden düzenleme, yeniden boyutlandırma, denetimleri ve Özellik Ekle veya aksi ilişkili Düzenleyicisi'ni kullanarak bir kaynak özelliklerini değiştirin. Bir kaynak olarak da düzenleyebilirsiniz [metin biçimi](../windows/how-to-open-a-resource-script-file-in-text-format.md) ve [ikili biçimi](../windows/opening-a-resource-for-binary-editing.md).  
  
 Bazı kaynak türleri içeri aktarıldı ve çeşitli şekillerde kullanılan tek dosyalardır; Bunlar, bit eşlemler, simgeler, işaretçiler, araç çubukları ve html dosyaları içerir. Dosya adları gibi kaynaklara sahip olarak [kaynak tanımlayıcıları](../windows/symbols-resource-identifiers.md). Diğer iletişim kutuları, menüler ve Win32 projeleri, dize tablolarında gibi yalnızca bir kaynak betiği (.rc) veya kaynak şablonu (.rct) dosyasının parçası olarak mevcut.  
  
> [!NOTE]
>  Kaynağın özelliklerini [Özellikler penceresini kullanarak değiştirilebilir](../windows/changing-the-properties-of-a-resource.md).  
  
## <a name="win32-resources"></a>Win32 kaynakları  
 Win32 kaynaklarında erişebileceğiniz [kaynak görünümü](../windows/resource-view-window.md) bölmesi.  
  
### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>Bir Win32 kaynağı kaynak düzenleyicide görüntülemek için  
  
1.  Seçin **kaynak görünümü** gelen **görünümü** menüsü.  
  
2.  Varsa **kaynak görünümü** penceresinin en üstünde pencere değil, tıklayın **kaynak görünümü** dön getirmek için sekmesinde.  
  
3.  Gelen **kaynak görünümü**, görüntülemek istediğiniz kaynakları içeren proje klasörünü genişletin. Örneğin, bir iletişim kutusu kaynağı görüntülemek istiyorsanız, genişletme **iletişim** klasör.  
  
    > [!NOTE]
    >  Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
4.  Örneğin, kaynağa çift tıklatın **IDD_ABOUTBOX**.  
  
     Kaynak uygun Düzenleyicisi'nde açılır. Örneğin, iç kaynak iletişim kutusu kaynakları için açılır **iletişim** Düzenleyici.  
  
     Ayrıca [görüntülemek kaynakları bir (kaynak betiği) .rc dosyasındaki açık bir projeniz zorunda kalmadan](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
### <a name="to-delete-an-existing-win-32-resource"></a>Mevcut bir Win 32 kaynağı silmek için  
  
1.  İçinde **kaynak görünümü**, bir kaynak türü için düğümü genişletin.  
  
2.  Sağ tıklayın ve silmek istediğiniz kaynak **Sil** kısayol menüsünden.  
  
    > [!NOTE]
    >  Bir belge penceresi dışında bir proje açın .rc dosyası varsa, aynı kısayol menü komutunu kullanarak kaynak silebilirsiniz.  
  
## <a name="resources-in-managed-projects"></a>Yönetilen projelerde kaynakları  
 Yönetilen projelere kaynak betik dosyalarına kullanmadığından kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>Yönetilen kaynak bir kaynak Düzenleyicisi'nde görüntülemek için  
  
1.  İçinde **Çözüm Gezgini**, kaynak, örneğin, çift **Bitmap1.bmp**.  
  
     Kaynak uygun Düzenleyicisi'nde açılır.  
  
### <a name="to-delete-an-existing-managed-resource"></a>Mevcut bir yönetilen kaynak silinemedi  
  
1.  İçinde **Çözüm Gezgini**, seçin ve silmek istediğiniz kaynağa sağ **Sil** kısayol menüsünden.  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)