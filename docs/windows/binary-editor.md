---
title: İkili Düzenleyici | Microsoft Docs
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
ms.openlocfilehash: aa381c42f03bcc77575464af8f8c53ca83e0af81
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650072"
---
# <a name="binary-editor"></a>İkili Düzenleyici
> [!WARNING]
>  **İkili düzenleyici** Express sürümlerinde kullanılamaz.  
  
 İkili Düzenleyicisi onaltılık veya ASCII biçiminde ikili düzeyde herhangi bir kaynağa düzenlemenizi sağlar. Ayrıca [Bul komut](/visualstudio/ide/reference/find-command) ASCII dizelerinde veya onaltılık baytlar için aranacak. Kullanmanız gereken **ikili** görüntülemek veya küçük yapmak yalnızca ihtiyacınız olduğunda Düzenleyicisi değişiklikleri özel kaynaklar veya kaynak türleri Visual Studio ortamı tarafından desteklenmiyor.  
  
 Açmak için **ikili düzenleyici**, ilk seçin **dosya** > **yeni** > **dosya** ana menüden dosyayı düzenleyin ardından yanındaki açılan oka tıklayın **açık** düğmesini ve ardından **birlikte Aç** > **ikili düzenleyici**.  
  
> [!CAUTION]
>  İletişim kutuları, resimler veya ikili düzenleyicide menüler gibi kaynakları düzenleme tehlikelidir. Yanlış düzenleme, kendi yerel düzenleyicisinde okunmaz hale gelir bir kaynak bozuk olabilir.  
  
> [!TIP]
>  Kullanırken **ikili** düzenleyicisinde birçok örneği sağ kaynağa özgü komutların kısayol menüsü görüntülenecek. Kullanılabilir komutlar ne imlecinizi işaret ettiği üzerinde bağlıdır. Örneğin, işaret ederken tıklarsanız **ikili** seçili onaltılık değerler düzenleyicisinde, kısayol menüsünü gösterir **Kes**, **kopyalama**, ve **Yapıştır**  komutları.  
  
 İle **ikili** Düzenleyicisi, şunları yapabilirsiniz:  
  
-   [İkili düzenleme için kaynak açma](../windows/opening-a-resource-for-binary-editing.md)  
  
-   [İkili verileri düzenleme](../windows/editing-binary-data.md)  
  
-   [İkili verileri bulma](../windows/finding-binary-data.md)  
  
-   [Yeni özel veya veri kaynağı oluşturun](../windows/creating-a-new-custom-or-data-resource.md)  
  
## <a name="managed-resources"></a>Yönetilen Kaynaklar  
 Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve **ikili** kaynak dosyalarıyla çalışmak için düzenleyici yönetilen projeleri. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)