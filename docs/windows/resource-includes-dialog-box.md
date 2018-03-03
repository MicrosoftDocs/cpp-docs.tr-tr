---
title: "Kaynak iletişim kutusu içeren | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.resourceincludes
dev_langs:
- C++
helpviewer_keywords:
- Resource Includes dialog box
- rc files, changing storage
- symbol header files, changing
- compiling source code, including resources
- .rc files, changing storage
- symbol header files, read-only
- symbols, symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 610e970ad84c6c89d91182b7a61bb759112fcd7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-includes-dialog-box"></a>Kaynak İçerikleri İletişim Kutusu
Kullanabileceğiniz **kaynağını içeren** tüm kaynaklar proje .rc dosyasını ve tüm depolama ortamı normal çalışma düzenleme değiştirmek için iletişim kutusu [simgeleri](../windows/symbols-resource-identifiers.md) Resource.h içinde.  
  
 Açmak için **kaynağını içeren** dosya iletişim kutusu, .rc bir sağ tıklayın [kaynak görünümü](../windows/resource-view-window.md), ardından **kaynağını içeren** kısayol menüsünden.  
  
 **Sembol üstbilgi dosyası**  
 Kaynak dosyanızı simge tanımlarını depolandığı üstbilgi dosyası adını değiştirmenize izin verir. Daha fazla bilgi için bkz: [sembol üstbilgi dosyaları adları değiştirme](../windows/changing-the-names-of-symbol-header-files.md).  
  
 **Salt okunur sembol yönergeleri**  
 Düzenleme oturumu sırasında değiştirilmemelidir sembolleri içeren üst bilgi dosyaları eklemenizi sağlar. Örneğin, birkaç projeler arasında paylaşılan bir simge dosyası içerebilir. MFC .h dosyaları de içerir. Daha fazla bilgi için bkz: [dahil olmak üzere paylaşılan (salt okunur) veya hesaplanan sembolleri](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 **Derleme zamanı yönergeleri**  
 Oluşturulan kaynak dosyaları içerir ve ana kaynak dosyanızdaki kaynaklardan ayrı olarak düzenlenmiş derleme zamanı yönergeleri (örneğin kaynaklar koşullu içeren) içeren veya özel bir biçim kaynaklarında içeremez izin verir. Standart MFC kaynak dosyaları dahil etmek için derleme zamanı yönergeleri kutusunu da kullanabilirsiniz. Daha fazla bilgi için bkz: [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).  
  
> [!NOTE]
>  Bu metin kutularındaki girişleri görünür tarafından işaretlenen .rc dosyasındaki `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, ve `TEXTINCLUDE 3` sırasıyla. Daha fazla bilgi için bkz: [TN035: kullanarak birden çok kaynak dosya ve üstbilgi dosyası Visual C++ ile](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).  
  
 Kullanarak, kaynak dosyaya değişiklikleri yaptıktan sonra **kaynağını içeren** iletişim kutusunda, gereken .rc dosyayı kapatın ve sonra da değişikliklerin etkili olması yeniden açın. Daha fazla bilgi için bkz: [derleme zamanında dahil olmak üzere kaynakları](../windows/how-to-include-resources-at-compile-time.md).  
  

  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: belirtin kaynaklar için dizin eklemeyi](../windows/how-to-specify-include-directories-for-resources.md)   
 [Semboller: Kaynak tanımlayıcılar](../windows/symbols-resource-identifiers.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)