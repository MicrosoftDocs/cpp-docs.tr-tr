---
title: "Kayıt görünümleri (MFC veri erişimi) için kullanıcı arabirimi güncelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: aab6ea73fc5726771877640268c89edea4d0745a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>Kayıt görünümleri (MFC veri erişimi) için kullanıcı arabirimi güncelleştiriliyor
`CRecordView`Varsayılan Gezinti komutları için kullanıcı arabirimi güncelleştirme işleyicileri sağlar. Bu işleyiciler etkinleştirme ve kullanıcı arabirimi nesneleri devre dışı bırakma otomatikleştirmek — menü öğeleri ve araç çubuğu düğmeleri. Uygulama Sihirbazı'nı Standart menüler sağlar ve seçerseniz **Dockable Araç çubuğu** seçeneği, bir dizi araç çubuğu düğmesi komutlar için. Kayıt görünümü sınıfını kullanarak oluşturursanız `CRecordView`, uygulamanız için kullanıcı arabirimi nesneleri eklemek isteyebilirsiniz.  
  
### <a name="to-create-menu-resources-with-the-menu-editor"></a>Menü düzenleyicisi menüsü kaynaklarını oluşturmak için  
  
1.  Kullanma hakkında bilgi için başvuran [Menü Düzenleyici](../windows/menu-editor.md), aynı dört komutla kendi menüsü oluşturabilir.  
  
#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>Araç çubuğu düğmeleri grafik Düzenleyicisi oluşturmak için  
  
1.  Kullanma hakkında bilgi için başvuran [araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md), araç çubuğu düğmeleri için kayıt gezinti komutlarınızı eklemek için araç çubuğu kaynağını düzenleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt Görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)   
 [Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)