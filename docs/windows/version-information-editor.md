---
title: Sürüm bilgileri Düzenleyicisi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version.F1
dev_langs:
- C++
helpviewer_keywords:
- Version Information editor, about Version Information editor
- editors, Version Information
- resource editors, Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e57e550527bc906d3c1170e410719c57a877eec
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647387"
---
# <a name="version-information-editor"></a>Sürüm Bilgileri Düzenleyicisi
Sürüm bilgileri, şirket ve ürün kimliği, bir ürün sürüm numarasını ve telif hakkı ve ticari marka bildirimini oluşur. Sürüm bilgileri Düzenleyicisi ile oluşturun ve sürüm bilgileri kaynağında depolanan bu verileri korumak. Sürüm bilgileri kaynağında bir uygulama tarafından gerekli değildir, ancak uygulamayı tanımlayan bilgileri toplamak için kullanışlı bir yerdir. Sürüm bilgileri de API'leri kurulum tarafından kullanılır.  
  
 Sürüm bilgileri kaynağında bir üst bloğu ve bir veya daha fazla alt blokları vardır: tek bir sabit bilgi bloğu üst ve alt (diğer diller ve/veya karakter kümesi için) bir veya daha fazla sürüm bilgi bloğu. Üst blok düzenlenebilir bir sayısal kutusu hem seçilebilir aşağı açılan listesi vardır. Alt bloklar yalnızca düzenlenebilir metin kutuları sahip.  
  
> [!NOTE]
>  Windows standart VS_VERSION_INFO adlı yalnızca bir sürümü kaynak sağlamaktır.  
  
 Sürüm bilgileri Düzenleyicisi ile yapabilecekleriniz:  
  
-   [Sürüm bilgileri kaynağında dize düzenleme](../windows/editing-a-string-in-a-version-information-resource.md)  
  
-   [(Yeni sürüm bilgi bloğu) başka bir dil için sürüm bilgileri ekleme](../windows/adding-version-information-for-another-language.md)  
  
-   [Sürüm bilgi bloğu silinsin](../windows/deleting-a-version-information-block.md)  
  
-   [Programınızdan erişim sürüm bilgileri](../windows/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  Sürüm bilgileri Düzenleyicisi'ni kullanırken, çoğu durumda, kaynağa özgü komutların kısayol menüsünü görüntülemek için sağ tıklayabilirsiniz. Örneğin, bir blok üstbilgisi girişine işaret ederken tıklarsanız, yeni sürüm blok bilgisi ve sürüm blok bilgisi silme komutları kısayol menüsünü gösterir.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [Menüler ve diğer kaynaklar](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)