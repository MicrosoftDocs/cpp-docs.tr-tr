---
title: "Nasıl yapılır: kopyalarken dilini veya koşulunu bir kaynağın değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.resvw.resource.changing
dev_langs: C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3655366e8851494482e628b9c260c796df3f64bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying"></a>Nasıl Yapılır: Kopyalarken Kaynağın Dilini veya Koşulunu Değiştirme
Bir kaynak olarak kopyalanırken dili özelliği veya koşul özelliği veya her ikisini de değiştirebilirsiniz.  
  
-   Kaynak dili tam olarak bunu, kaynak dilini tanımlar. Bu tarafından kullanılan [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) kendisi için aramanız kaynak tanımlamaya yardımcı olmak için. (Ancak, kaynakları her metne, örneğin, Japonca klavyede yalnızca çalışabilir Hızlandırıcıları veya yalnızca yerelleştirilmiş Çince için uygun olacak bir bit eşlem derlemeler ilişkili olmayan dil, vb. için farklılıklar olabilir.)  
  
-   Bir kaynağı tanımlayan bir koşul altında bu belirli kaynak kullanılacak kopyasıdır tanımlı bir simge durumdur.  
  
 Dil ve kaynak durumunu çalışma penceresinde kaynak adından sonra parantez içinde gösterilmektedir. Bu örnekte kendi dili olarak Fince IDD_AboutBox adlı kaynak kullanıyor ve XX33 kendi durumdur.  
  
```  
IDD_AboutBox (Finnish - XX33)  
```  
  
### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>Mevcut bir kaynağı kopyalayıp kendi dilini veya koşulunu değiştirme  
  
1.  .Rc dosya ya da buna [kaynak görünümü](../windows/resource-view-window.md) penceresinde, kopyalamak istediğiniz kaynak sağ tıklayın.  
  
2.  Seçin **Ekle kopyalama** kısayol menüsünden.  
  
3.  İçinde **Ekle kaynak kopyası** iletişim kutusunda:  
  
    -   İçin **dil** liste kutusunda, dili seçin.  
  
    -   İçinde **koşulu** koşulu yazın.  
  

  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: kaynakları kopyalama](../windows/how-to-copy-resources.md)   
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)