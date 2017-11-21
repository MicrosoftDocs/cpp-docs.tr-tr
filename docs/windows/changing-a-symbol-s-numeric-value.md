---
title: "S sayısal değerini bir simge &#39; değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.symbol.changing.value
dev_langs: C++
helpviewer_keywords:
- numeric values
- symbols, numeric values
- numeric values, changing symbols
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 97a6def651826ae71cecf33f751f8c0858c691dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="changing-a-symbol39s-numeric-value"></a>S sayısal değerini bir simge &#39; değiştirme
Tek bir kaynakla ilişkili simgelerini kullandığınız [Özellikler penceresini](/visualstudio/ide/reference/properties-window) simge değerini değiştirmek için. Kullanabileceğiniz [kaynak sembolleri iletişim kutusu](../windows/resource-symbols-dialog-box.md) bir kaynağa atanmış simge değerini değiştirmek için. Daha fazla bilgi için bkz: [atanmamış sembolleri değiştirme](../windows/changing-unassigned-symbols.md).  
  
### <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>Bir tek bir kaynak veya nesne atanmış bir simge değerini değiştirmek için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md), kaynağı seçin.  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde **özellikleri** penceresinde, türü sembol adını ve ardından bir eşittir işareti ve bir tamsayı olarak **kimliği** kutusunda, örneğin:  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 Yeni değer projeyi bir sonraki kaydettiğinizde sembol üstbilgi dosyasında depolanır. Yalnızca simge adı Kimliği kutusunda görünür; Bunlar doğrulandıktan sonra eşittir işareti ve değer görüntülenmez.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında bilgi için ve [izlenecek yol: kullanarak kaynakları yerelleştirme ASP.NETile](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sembol değeri kısıtlamaları](../windows/symbol-value-restrictions.md)   
 [Önceden tanımlanmış sembol kimlikleri](../windows/predefined-symbol-ids.md)