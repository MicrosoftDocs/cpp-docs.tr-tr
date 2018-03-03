---
title: "İkili Düzenleyicisi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.binary.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, Binary
- resources [Visual Studio], editing
- resource editors, Binary editor
- Binary editor
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4dade674fb32615e23904e6dbaf03d6c6ee0a371
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="binary-editor"></a>İkili Düzenleyici
> [!WARNING]
>  İkili Düzenleyicisi'ni Express sürümlerinde kullanılabilir değil.  
  
 İkili Düzenleyicisi on altılı veya ASCII biçiminde ikili düzeyde herhangi bir kaynağa düzenlemenize olanak sağlar. Aynı zamanda [Bul komutu](/visualstudio/ide/reference/find-command) ASCII dizeleri veya onaltılık baytlar için aranacak. Yalnızca görüntülemek veya özel kaynaklar veya Visual Studio ortamı tarafından desteklenmeyen kaynak türleri küçük değişiklikler yapmak gereksinim duyduğunuzda, İkili Düzenleyicisi'ni kullanmanız gerekir.  
  
 İkili Düzenleyicisi'ni açmak için öncelikle seçin **dosyası &#124; Yeni &#124; Dosya** ana menüden düzenleyin, sonra yanındaki açılan oka tıklayın istediğiniz dosyayı seçin **açık** düğmesine tıklayın ve seçin **birlikte Aç &#124; İkili Düzenleyicisi**.  
  
> [!CAUTION]
>  İletişim kutuları, görüntü veya İkili Düzenleyicisi menülerde gibi kaynakları düzenleme tehlikeli. Yanlış düzenleme kendi yerel düzenleyicisinde okunamaz hale getirme kaynak bozuk olabilir.  
  
> [!TIP]
>  Çoğu durumda İkili Düzenleyicisi ' ni kullanırken, kaynak özgü komutlar bir kısayol menüsünü görüntülemek için sağ tıklayabilirsiniz. Kullanılabilir komutlar ne imlecinizi işaret ettiğinden üzerinde bağlıdır. Örneğin, seçili onaltılık değerler ile İkili Düzenleyicisi işaret ederken tıklarsanız, kısayol menüsünü gösterir **Kes**, **kopya**, ve **Yapıştır** komutları.  
  
 İkili Düzenleyicisi ile şunları yapabilirsiniz:  
  
-   [Bir kaynağı ikili düzenleme için açma](../windows/opening-a-resource-for-binary-editing.md)  
  
-   [İkili verileri düzenleme](../windows/editing-binary-data.md)  
  
-   [İkili verileri bulma](../windows/finding-binary-data.md)  
  
-   [Yeni bir özel veya veri kaynağı oluşturma](../windows/creating-a-new-custom-or-data-resource.md)  
  
## <a name="managed-resources"></a>Yönetilen Kaynaklar  
 Kullanabileceğiniz [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md) ve yönetilen projelerde kaynak dosyalarıyla çalışmak için ikili Düzenleyici. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)

