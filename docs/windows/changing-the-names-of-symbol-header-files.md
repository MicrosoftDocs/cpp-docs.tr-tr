---
title: "Sembol başlık dosyalarının adlarını değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.symbol.changing.header
dev_langs: C++
helpviewer_keywords:
- resource files, multiple
- Resource Includes dialog box
- symbol header files, changing names
- symbol header files
- header files, changing names
- names [C++], symbol header files
- symbols, symbol header files
- Resource.h
ms.assetid: b948284a-7899-402e-ab12-9f2c8480ca9d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ccc7cc8662e33e5999ceafbcd8f029e2675341b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-names-of-symbol-header-files"></a>Sembol Başlık Dosyalarının Adlarını Değiştirme
Normalde tüm simge tanımlarını Resource.h kaydedilir. Ancak, bu değiştirmeniz gerekebilir, örneğin, aynı dizinde birden fazla kaynak dosyayla çalışabilirsiniz böylece dosya adını içerir.  
  
### <a name="to-change-the-name-of-the-resource-symbol-header-file"></a>Kaynak sembol üstbilgi dosyası adını değiştirmek için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md).rc dosyasını sağ tıklatın ve seçin [kaynağını içeren](../windows/resource-includes-dialog-box.md) kısayol menüsünden.  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  İçinde **sembol üstbilgi dosyası** içerme dosyası için yeni adı yazın.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.*  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak sembolleri görüntüleme](../windows/viewing-resource-symbols.md)   
 [Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)