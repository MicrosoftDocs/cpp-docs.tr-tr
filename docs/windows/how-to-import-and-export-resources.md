---
title: 'Nasıl yapılır: içeri ve dışarı aktarma kaynakları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.importing
- vc.resvw.resource.importing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [Visual Studio], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e526ab335436730f4132b5b7127ec9079432a4a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879184"
---
# <a name="how-to-import-and-export-resources"></a>Nasıl Yapılır: Kaynakları İçeri ve Dışarı Aktarma
Grafik kaynakları (bit eşlemler, simgeler, imleçler ve araç çubuklarını), HTML dosyaları ve özel kaynakların Visual C++'ta kullanmak için içeri aktarabilirsiniz. Geliştirme ortamı dışında kullanılan dosyaları ayırmak için bir Visual C++ projeden dosyaları aynı türde dışarı aktarabilirsiniz.  
  
> [!NOTE]
>  Dize tabloları hızlandırıcıları ve iletişim kutuları gibi kaynak türleri alınamaz veya değil tek başına dosya türleri olduğundan verilemez.  
  
### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>Tek başına bir kaynak geçerli kaynak dosyanızı içe aktarmak için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md), bir kaynak betik düğüme sağ tıklayın (* .rc) kaynak eklemek istediğiniz dosya.  
  
2.  Tıklatın **alma** kısayol menüsünde.  
  
3.  Bulun ve seçerlerse, simge (.ico), imleç (.cur), Html dosyası (.htm) veya içeri aktarmak istediğiniz diğer dosya dosya adını seçin.  
  
4.  Tıklatın **Tamam** seçili dosyada kaynak eklemek için **kaynak** görünümü.  
  
    > [!NOTE]
    >  Aynı şekilde hangi belirli kaynak olsun türünü içeri aktarma işlemi works seçtiniz. Alınan kaynak, kaynak türü için doğru düğümü otomatik olarak eklenir.  
  
### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>Bir bitmap, simgesi veya imleci (kullanmak için Visual C++ dışında) ayrı bir dosya olarak dışarı aktarmak için  
  
1.  İçinde **kaynak** görüntülemek için dışarı aktarmak istediğiniz kaynak sağ tıklayın.  
  
2.  Tıklatın **verme** kısayol menüsünde.  
  
3.  İçinde **verme kaynak** iletişim kutusunda, geçerli dosya adı kabul edin veya yeni bir tane yazın.  
  
4.  Dosyayı kaydedin ve tıklatın istediğiniz klasöre gidin **verme**.  
  

  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)