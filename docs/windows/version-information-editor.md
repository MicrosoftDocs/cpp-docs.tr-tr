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
ms.openlocfilehash: 76a76dbb3d8b41c2366f354f9c3c8d66ccc3743f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890596"
---
# <a name="version-information-editor"></a>Sürüm Bilgileri Düzenleyicisi
Sürüm bilgileri, şirket ve ürün kimliği, bir ürün sürüm numarasını ve telif hakkı ve marka bildirim oluşur. Sürüm bilgileri Düzenleyicisi ile oluşturun ve sürüm bilgileri kaynağında depolanan bu verileri güncelleştirin. Sürüm bilgileri kaynağında bir uygulama tarafından gerekli değildir, ancak uygulama tanımlayan bilgileri toplamak için yararlı bir yerdir. Sürüm bilgileri de API'leri kurulum tarafından kullanılır.  
  
 Sürüm bilgileri kaynağında bir üst bloğu ve bir veya daha fazla alt bloklar vardır: tek bir sabit bilgi bloğu üst ve alt (diğer diller ve/veya karakter kümesi için) bir veya daha fazla sürüm bilgi bloğu. Üst blok düzenlenebilir sayısal kutuları ve seçilebilir açılan listeleri vardır. Alt bloklar yalnızca düzenlenebilir metin kutularına sahiptir.  
  
> [!NOTE]
>  Windows standart VS_VERSION_INFO adlı yalnızca bir sürümü kaynak olmalıdır.  
  
 Sürüm bilgileri Düzenleyicisi sağlar:  
  
-   [Sürüm bilgileri kaynağında dizesinde Düzenle](../windows/editing-a-string-in-a-version-information-resource.md)  
  
-   [Başka bir dilde (yeni sürüm bilgi bloğu) için sürüm bilgileri ekleme](../windows/adding-version-information-for-another-language.md)  
  
-   [Sürüm bilgileri bloğunu silme](../windows/deleting-a-version-information-block.md)  
  
-   [Programınızdan erişim sürüm bilgileri](../windows/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  Sürüm bilgileri Düzenleyicisi'ni kullanırken, çoğu durumda kaynak özgü komutlar bir kısayol menüsünü görüntülemek için sağ tıklatın. Örneğin, bir blok üstbilgisi girişine işaret ederken tıklarsanız, yeni sürüm blok bilgisi ve sürüm blok bilgisi silme komutlarını kısayol menüsünü gösterir.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak düzenleyicileri](../windows/resource-editors.md)   
 [Menüler ve diğer kaynaklar](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)

