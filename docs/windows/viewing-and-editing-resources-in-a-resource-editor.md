---
title: "Görüntüleme ve kaynakları kaynak düzenleyicisinde düzenleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 980264ab1857af214dcd24703980b8efa9a4d2dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="viewing-and-editing-resources-in-a-resource-editor"></a>Kaynakları, Kaynak Düzenleyicisinde Görüntüleme ve Düzenleme
Her kaynak türü bu kaynak türü için belirli bir kaynak düzenleyicisine sahiptir. Yeniden, yeniden boyutlandırma, denetimleri ve özellik ekleme veya aksi halde ilişkili Düzenleyicisi'ni kullanarak bir kaynak yönlerini değiştirin. Bir kaynak olarak da düzenleyebilirsiniz [metin biçimi](../windows/how-to-open-a-resource-script-file-in-text-format.md) ve [ikili biçimi](../windows/opening-a-resource-for-binary-editing.md).  
  
 Bazı kaynak türleri, içe aktarılan ve çeşitli şekillerde kullanılan tek tek dosyalarıdır; Bunlar, bit eşlemler, simgeler, imleçler, araç çubukları ve html dosyaları içerir. Dosya adları gibi kaynaklarınız yanı [kaynak tanımlayıcılar](../windows/symbols-resource-identifiers.md). Diğer iletişim kutuları, menüler ve Win32 projeleri, dize tablolarında gibi yalnızca bir kaynak (.rc) komut dosyası veya kaynak şablonu (.rct) dosyasının parçası olarak mevcut.  
  
> [!NOTE]
>  Kaynağın özelliklerini [Özellikler penceresini kullanarak değiştirilebilir](../windows/changing-the-properties-of-a-resource.md).  
  
## <a name="win32-resources"></a>Win32 kaynakları  
 Win32 kaynaklara erişim [kaynak görünümü](../windows/resource-view-window.md) bölmesi.  
  
#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>Win32 kaynak bir kaynak düzenleyicisinde görüntülemek için  
  
1.  Seçin **kaynak görünümü** gelen **Görünüm** menüsü.  
  
2.  Kaynak Görünümü penceresi en üst pencere değilse tıklatın **kaynak görünümü** sekmesini en üstüne getirin.  
  
3.  Kaynak görünümünden görüntülemek istediğiniz kaynakları içeren proje klasörünü genişletin. Örneğin, bir iletişim kutusu kaynağı görüntülemek istiyorsanız, iletişim klasörünü genişletin.  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
4.  Örneğin, IDD_ABOUTBOX kaynak çift tıklayın.  
  
     Kaynak uygun Düzenleyicisi'nde açar. Örneğin, iletişim kutusu kaynakları için kaynak içinde iletişim kutusu Düzenleyicisi açılır.  
  
     Ayrıca [görüntülemek kaynakları bir .rc (kaynak komut dosyası) dosyasına açık bir projeniz gerek kalmadan](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
#### <a name="to-delete-an-existing-win-32-resource"></a>Varolan bir Win 32 kaynağı silmek için  
  
1.  Kaynak Görünümü'nde, bir kaynak türü için düğümü genişletin.  
  
2.  Silin ve seçmek istediğiniz kaynak sağ **silmek** kısayol menüsünden.  
  
    > [!NOTE]
    >  Proje dışındaki bir belge penceresinde .rc dosyayı olduğunda aynı kısayol menü komutu kullanarak bir kaynak silebilirsiniz.  
  
## <a name="resources-in-managed-projects"></a>Yönetilen projelerinde kaynakları  
 Yönetilen projeleri kaynak betik dosyaları kullanmadığından kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md) ve [İkili Düzenleyicisi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
#### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>Yönetilen bir kaynağın kaynak düzenleyicisinde görüntülemek için  
  
1.  Çözüm Gezgini'nde, kaynak, örneğin, Bitmap1.bmp çift tıklayın.  
  
     Kaynak uygun Düzenleyicisi'nde açar.  
  
#### <a name="to-delete-an-existing-managed-resource"></a>Mevcut bir yönetilen kaynağı silmek için  
  
1.  Çözüm Gezgini'nde silin ve seçmek istediğiniz kaynak sağ **silmek** kısayol menüsünden.  
  
### <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)

