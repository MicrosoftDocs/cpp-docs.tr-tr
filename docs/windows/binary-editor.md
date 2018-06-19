---
title: İkili Düzenleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d5deb511069830de5ea7aa542bb010f57be5af9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857863"
---
# <a name="binary-editor"></a>İkili Düzenleyici
> [!WARNING]
>  İkili Düzenleyicisi'ni Express sürümlerinde kullanılabilir değil.  
  
 İkili Düzenleyicisi on altılı veya ASCII biçiminde ikili düzeyde herhangi bir kaynağa düzenlemenize olanak sağlar. Aynı zamanda [Bul komutu](/visualstudio/ide/reference/find-command) ASCII dizeleri veya onaltılık baytlar için aranacak. Yalnızca görüntülemek veya özel kaynaklar veya Visual Studio ortamı tarafından desteklenmeyen kaynak türleri küçük değişiklikler yapmak gereksinim duyduğunuzda, İkili Düzenleyicisi'ni kullanmanız gerekir.  
  
 İkili Düzenleyicisi'ni açmak için öncelikle seçin **dosya &#124; yeni &#124; dosya** ana menüden düzenleyin, sonra yanındaki açılan oka tıklayın istediğiniz dosyayı seçin **açmak** düğmesine tıklayın ve seçin**Birlikte Aç &#124; İkili Düzenleyicisi**.  
  
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

