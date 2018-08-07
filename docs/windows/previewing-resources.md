---
title: Kaynakları Önizleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- resource previews
- code, viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ff41dd0aad30382eb5229679054a74526652737
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605025"
---
# <a name="previewing-resources"></a>Kaynakları Önizleme
Kaynaklarınızı Önizleme açmaya gerek kalmadan grafik kaynak görüntülemenize olanak sağlar. Kaynak Tanımlayıcıları sayılara değiştiğinden bunlara derlenmiş sonra Önizleme de yürütülebilir dosyalar için yararlıdır. Bu sayısal tanımlayıcıları genellikle yeterli bilgi sağlamayan olduğundan, kaynakları Önizleme hızlıca belirlemenize yardımcı olur.  
  
 Görsel düzeni aşağıdaki kaynak türlerinin önizlemesini görebilirsiniz:  
  
-   Bit eşlem  
  
-   İletişim kutusu  
  
-   Simge  
  
-   Menü  
  
-   İmleç  
  
-   Araç Çubuğu  
  
 Görsel Önizleme işlevi Hızlandırıcı, bildirimi, dize tablosu ve sürüm bilgileri kaynakları için geçerli değildir.  
  
### <a name="to-preview-resources"></a>Kaynakları Önizleme  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md) veya belge penceresi, örneğin, IDD_ABOUTBOX kaynağınızı seçin.  
  
     **Not** projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), tıklayın **özellik sayfaları** düğmesi.  
  
     \- veya -  
  
3.  Üzerinde **görünümü** menüsünü tıklatın **özellik sayfaları**.  
  
     Bu kaynağın önizlemesini görüntüleme kaynak için özellik sayfasını açar. Yukarı ve aşağı ağaç denetimi kaynak görünümü ya da belge penceresini içinde gezinmek için ok tuşlarını. Özellik sayfasını açık kalır ve odaklı ve önizlemesi mümkün olan herhangi bir kaynağa göster.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler 
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Proje Dışındaki Kaynak Betik Dosyasını Açma (Tek Başına)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)