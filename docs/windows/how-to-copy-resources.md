---
title: 'Nasıl yapılır: kaynakları kopyalama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], moving between files
- resources [Visual Studio], copying
- resource files, copying or moving resources between
- resource files, tiling
- .rc files, copying resources between
- rc files, copying resources between
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4b173be24e9f177a3156f740fcb07240c30fec75
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879854"
---
# <a name="how-to-copy-resources"></a>Nasıl Yapılır: Kaynakları Kopyalama
Kaynakları bir dosyasından diğerine bunları değiştirmeden kopyalayabilirsiniz veya yapabilecekleriniz [dilini veya koşulunu bir kaynağın kopyalama sırasında değiştirmek](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).  
  
 Daha kolay kaynakları bir var olan kaynak veya yürütülebilir dosyayı geçerli kaynak dosyanızı kopyalayabilirsiniz. Bunu yapmak için aynı anda kaynakları içeren iki dosyaları açmak ve öğeleri bir dosyadan sürükleyin veya kopyalayıp iki dosya arasında yapıştırın. Bu yöntem, kaynak betik (.rc) dosyaları ve kaynak şablonu (.rct) dosyaları, yanı sıra için çalıştırılabilir (.exe) dosyaları çalışır.  
  
> [!NOTE]
>  Visual C++, kendi uygulamanızda kullanabilirsiniz örnek kaynak dosyalarını içerir. Daha fazla bilgi için bkz: [küçük resim: ortak kaynakları](http://msdn.microsoft.com/en-us/9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 Açık .rc dosyaları arasında sürükle ve bırak yöntemini kullanabilirsiniz [proje dışında](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>Kaynaklar arasında sürükle ve bırak yöntemini kullanarak dosyaları kopyalamak için  
  
1.  Tek başına hem de kaynak dosyalarını açın (daha fazla bilgi için bkz: [.rc dosyası dışında of proje görüntüleme kaynaklarında](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Örneğin, Source1.rc ve Source2.rc açın.  
  
2.  İlk .rc dosyası kopyalamak istediğiniz kaynak'ı tıklatın. Örneğin, Source1.rc içinde IDD_DIALOG1'ı tıklatın.  
  
3.  CTRL tuşunu basılı tutun ve kaynak ikinci .rc dosyasına sürükleyin. Örneğin, IDD_DIALOG1 Source1.rc Source2.rc için sürükleyin.  
  
    > [!NOTE]
    >  CTRL tuşunu basılı tutup olmadan kaynak sürükleyerek kopyalamak yerine kaynak taşır.  
  
### <a name="to-copy-resources-using-copy-and-paste"></a>Kopyalama kullanarak kaynakları kopyalamak ve yapıştırmak için  
  
1.  Tek başına hem de kaynak dosyalarını açın (daha fazla bilgi için bkz: [.rc dosyası dışında of proje görüntüleme kaynaklarında](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Örneğin, Source1.rc ve Source2.rc.  
  
2.  Bir kaynak içinden istediğiniz bir kaynak (örneğin, Source1.rc) kopyalamak kaynak dosyasına sağ tıklayın ve seçin **kopyalama** kısayol menüsünden.  
  
3.  Kaynak (örneğin, Source2.rc) yapıştırın istediğiniz kaynak dosyasını sağ tıklatın. Seçin **Yapıştır** kısayol menüsünden.  
  
    > [!NOTE]
    >  Sürükleme ve bırakma, kopyalayamaz, kesme veya kaynak dosyaları (Kaynak Görünümü) projesinde ve tek başına .rc dosyaları (Bu belge windows açık) arasında yapıştırın. Bu ürünün önceki sürümlerinde yapabilirsiniz.  
  
    > [!NOTE]
    >  Yeni dosyasına kopyaladığınızda sembol adları veya var olan dosyayı değerleri ile çakışmaları önlemek için Visual C++ aktarılan kaynağın sembol değeri veya sembol adını ve değerini değiştirebilir.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: (tek başına) proje dışındaki kaynak betik dosyasını açın](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)