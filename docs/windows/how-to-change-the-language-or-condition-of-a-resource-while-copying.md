---
title: 'Nasıl yapılır: kopyalarken dilini veya koşulunu bir kaynağın değiştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.changing
dev_langs:
- C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fcddbc0bb5a2afe807cbe8ca7643a831c28ad50f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
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