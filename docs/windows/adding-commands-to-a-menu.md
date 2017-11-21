---
title: "Menüye komut ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.menu
dev_langs: C++
helpviewer_keywords:
- menu items, adding to menus
- menus, adding items
- commands, adding to menus
- commands
- menu items
ms.assetid: 1523a755-0ab5-42f8-9e98-bb9881564431
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ccbfe6543854dc6a904d80c9e483dfde8122327a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-commands-to-a-menu"></a>Menüye Komut Ekleme
### <a name="to-add-commands-to-a-menu"></a>Menüye komut eklemek için  
  
1.  [Menü oluşturmak](../windows/creating-a-menu.md).  
  
2.  Örneğin, dosya bir menü adına tıklayın.  
  
     Her menüye genişletin ve komutlar için yeni bir öğe kutusu kullanıma sunar. Örneğin, komutları yeni Ekle açın ve bir dosya menüsüne kapatın.  
  
3.  Yeni öğe kutusunda, yeni menü komutu için bir ad yazın.  
  
    > [!NOTE]
    >  Menü Düzenleyici hem de yazdığınız metin görünür **resim yazısı** kutusunda [Özellikler penceresini](/visualstudio/ide/reference/properties-window). Her iki konumda yeni menünüze için özelliklerini düzenleyin.  
  
    > [!TIP]
    >  Menü komutunu seçmek kullanıcının sağlayan bir kısayol tuşu (sık kullanılan tuş) tanımlayabilirsiniz. Yazın ve işareti (&) anımsatıcı belirtmek için bir harf önünde. Kullanıcı, o harfi yazarak menü komutu seçebilirsiniz.  
  
4.  Özellikler penceresinde uygulamak menü komut özellikleri seçin. Ayrıntılar için bkz [menü komut özellikleri](../windows/menu-command-properties.md).  
  
5.  İçinde **istemi** Özellikler penceresinde kutusuna, uygulamanızın durum çubuğunda görünmesini istem dizesi yazın.  
  
     Bu, oluşturduğunuz menü komutu ile aynı kaynak tanımlayıcıyla dize tablosunda bir giriş oluşturur.  
  
    > [!NOTE]
    >  Komut istemlerini ile menü öğesi için yalnızca uygulayabileceğiniz bir **açılan** özelliği **doğru**. Örneğin, alt menü öğeleri varsa en üst düzey menü öğeleri istemleri olabilir. Ne olacağını belirtmek için bir istem amacı olan bir kullanıcı menü öğesi tıklarsa.  
  
6.  Tuşuna **ENTER** menü komut tamamlanamadı.  
  
     Ek menü komutlarını oluşturabilmesi için yeni öğe kutusu seçilidir.  
  

  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menü düzenleyicisi](../windows/menu-editor.md)   
