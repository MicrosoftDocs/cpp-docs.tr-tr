---
title: "Hızlandırıcı tablosunu giriş ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fe2df81aae0b9b7232443de1db091a9cbb0c0d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>Hızlandırıcı Tablosunu Giriş Ekleme
### <a name="to-add-an-entry-to-an-accelerator-table"></a>Hızlandırıcı tablosunu giriş eklemek için  
  
1.  Hızlandırıcı tablosunu simgesini çift tıklatarak açın [kaynak görünümü](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Hızlandırıcı tablo içinde sağ tıklatın ve seçin **yeni hızlandırıcı** kısayol menüsünden veya tablonun sonuna boş satır girişi'ı tıklatın.  
  
3.  Seçin bir [kimliği](id-property.md) kimliği aşağı açılan listeden kutusu veya yeni bir kimliği yazın **kimliği** kutusu.  
  
4.  Türü [anahtar](../windows/accelerator-key-property.md) Hızlandırıcı veya sağ olarak kullanın ve seçmek istediğiniz **sonraki anahtar yazılan** bir tuş bileşimini ayarlamak için kısayol menüsünden ( **sonraki anahtar yazılan** komutu Ayrıca kullanılabilir **Düzenle** menüsü).  
  
5.  Değişiklik [değiştiricisi](../windows/accelerator-modifier-property.md) ve [türü](../windows/accelerator-type-property.md)gerekirse,.  
  
6.  Tuşuna **ENTER**.  
  
    > [!NOTE]
    >  Tanımladığınız tüm Hızlandırıcıları benzersiz olduğundan emin olun. Aynı kimliği hatalı hiçbir etkisi olmadan atanan birkaç tuş bileşimlerini olabilir, örneğin, CTRL + P ve F8 her ikisi için ID_PRINT atanabilir. Ancak, bir tuş bileşimini sahip birden fazla kimliği de, örneğin, işe yaramaz atanmış CTRL + Z ID_SPELL_CHECK ve ID_THESAURUS atanmış.  
  

  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tablolarını düzenleme](../windows/editing-accelerator-tables.md)   
 [Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)