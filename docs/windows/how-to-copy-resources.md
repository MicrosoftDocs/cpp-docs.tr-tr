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
ms.openlocfilehash: f29a115d20eca90b66a876bf1b5070052d90008d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570691"
---
# <a name="how-to-copy-resources"></a>Nasıl Yapılır: Kaynakları Kopyalama
Kaynakları bir dosyadan başka değişiklik yapmadan kopyalayabilir veya yapabilecekleriniz [dilini veya koşulunu kaynağının bu kopyalarken değiştirme](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).  
  
 Kolayca kaynakları bir var olan bir kaynak veya yürütülebilir dosyanın geçerli kaynak dosyaya kopyalayabilirsiniz. Bunu yapmak için kaynakları içeren aynı anda hem dosyaları açmak ve öğeleri bir dosyadan sürükleyin veya kopyalayıp iki dosya arasında. Bu yöntem, kaynak betiği (.rc) dosyalarını ve kaynak şablonu (.rct) dosyaları, ek olarak yürütülebilir (.exe) dosyaları çalışır.  
  
> [!NOTE]
>  Visual C++, kendi uygulamanızda kullanabileceğiniz örnek kaynak dosyalarını içerir. Daha fazla bilgi için [küçük: ortak kaynaklar](http://msdn.microsoft.com/9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 Açık olan .rc dosyası arasında sürükle ve bırak yöntemi kullanabileceğiniz [proje dışında](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>Sürükle ve bırak yöntemiyle dosyaları arasında kaynakları kopyalama  
  
1.  Tek başına hem de kaynak dosyalarını açın (daha fazla bilgi için [bir .rc dosyasının dışında sonuna bir proje içinde kaynaklar görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Örneğin, Source1.rc ve Source2.rc açın.  
  
2.  İlk .rc dosyası kopyalamak istediğiniz kaynağa tıklayın. Örneğin Source1.rc içinde tıklayın **IDD_DIALOG1**.  
  
3.  CTRL tuşunu basılı tutun ve ikinci .rc dosyası için kaynak sürükleyin. Örneğin, sürükleyin **IDD_DIALOG1** Source1.rc Source2.rc için gelen.  
  
    > [!NOTE]
    >  Kaynak CTRL tuşu basılı tutulmadan sürükleyerek kopyalamak yerine kaynak taşır.  
  
### <a name="to-copy-resources-using-copy-and-paste"></a>Kopyalama kullanarak kaynakları kopyalamak ve yapıştırmak için  
  
1.  Tek başına hem de kaynak dosyalarını açın (daha fazla bilgi için [bir .rc dosyasının dışında sonuna bir proje içinde kaynaklar görüntüleme](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Örneğin, Source1.rc ve Source2.rc.  
  
2.  Bir kaynak, istediğiniz bir kaynak (örneğin, Source1.rc) kopyalamak kaynak dosyasında sağ tıklatıp seçin **kopyalama** kısayol menüsünden.  
  
3.  Kaynak (örneğin, Source2.rc) yapıştırmak istediğiniz kaynak dosyaya sağ tıklayın. Seçin **Yapıştır** kısayol menüsünden.  
  
    > [!NOTE]
    >  Sürükleyin ve bırakın, kopyalayamaz, Kes veya ' % s'projesi (Kaynak Görünümü) kaynak dosyalarında ve tek başına .rc dosyaları (Bu belge pencerelerinin açık) arasında yapıştırın. Bu ürünün önceki sürümlerinde yapabilirsiniz.  
  
    > [!NOTE]
    >  Yeni dosyayı kopyaladığınızda, sembol adlarını veya var olan dosyayı değerleri ile çakışmaları önlemek için Visual C++ aktarılan kaynak sembol değeri veya sembol adını ve değerini değişebilir.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Proje Dışındaki Kaynak Betik Dosyasını Açma (Tek Başına)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)