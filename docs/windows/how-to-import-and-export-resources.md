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
ms.openlocfilehash: e912e2aaae53fa0c7f9e506ce70128238bf15a78
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018422"
---
# <a name="how-to-import-and-export-resources"></a>Nasıl Yapılır: Kaynakları İçeri ve Dışarı Aktarma
Grafik kaynakları (bit eşlemler, simgeler, işaretçiler ve araç çubukları), HTML dosyaları ve Visual C++'ta kullanmak için özel kaynaklar içeri aktarabilirsiniz. Geliştirme ortamının dışında kullanılan dosyaları ayırmak için bir Visual C++ projesi aynı dosya türlerini dışarı aktarabilirsiniz.  
  
> [!NOTE]
>  Dize tabloları hızlandırıcıları ve iletişim kutuları gibi kaynak türleri içeri aktarılabilir veya tek başına dosya türleri değil olduklarından dışarı.  
  
### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>Tek bir kaynağın geçerli kaynak dosyanızı içeri aktarmak için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md), düğümü için kaynak betiği (* .rc) bir kaynak eklemek istediğiniz dosya.  
  
2.  Tıklayın **alma** kısayol menüsünde.  
  
3.  Bulun ve bit eşlem (.bmp), simge (.ico), imleç (.cur), Html dosyası (.htm) veya içeri aktarmak istediğiniz başka bir dosyayı dosya adını seçin.  
  
4.  Tıklayın **Tamam** 'teki Seçili dosyanın kaynak eklemek için **kaynak** görünümü.  
  
    > [!NOTE]
    >  Belirli kaynağı ne olursa olsun aynı şekilde türünü içeri aktarma işlemi works seçtiniz. İçeri aktarılan kaynak otomatik olarak bu kaynak türü için doğru düğümüne eklenir.  
  
### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>Bir bit eşlem, simgesi veya imleci (Visual C++ dışında kullanın için) ayrı bir dosya olarak dışarı aktarmak için  
  
1.  İçinde **kaynak** görüntülemek için dışa aktarmak istediğiniz kaynağa sağ tıklayın.  
  
2.  Tıklayın **dışarı** kısayol menüsünde.  
  
3.  İçinde **kaynağı dışarı aktarın** iletişim kutusunda, geçerli dosya adı kabul edin veya yeni bir tane girin.  
  
4.  Dosyayı kaydedin ve tıklayın istediğiniz klasöre gidin **dışarı**.  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)