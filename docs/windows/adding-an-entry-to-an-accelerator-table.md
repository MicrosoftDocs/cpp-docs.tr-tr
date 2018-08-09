---
title: Hızlandırıcı tablosunu giriş ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e0c5e94913a705ac97407f82075ff9c83a12dd6b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642795"
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>Hızlandırıcı Tablosunu Giriş Ekleme
### <a name="to-add-an-entry-to-an-accelerator-table"></a>Hızlandırıcı tablosunu giriş ekleme  
  
1.  Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Hızlandırıcı tablosu içinde sağ tıklatın ve seçin **yeni hızlandırıcı** kısayol menüsünden veya tablonun alt kısmındaki boş satır girdiye tıklayın.  
  
3.  Seçin bir [kimliği](id-property.md) kimliği aşağı açılan listeden kutusuna veya yeni bir kimliği yazın **kimliği** kutusu.  
  
4.  Türü [anahtarı](../windows/accelerator-key-property.md) bir Hızlandırıcı veya sağ tıklayarak kullanın ve isteyip **sonraki anahtarı yazılan** bir tuş bileşimi ayarlamak için kısayol menüsünden ( **sonraki anahtarı yazılan** komutu Ayrıca kullanılabilir **Düzenle** menü).  
  
5.  Değişiklik [değiştiricisi](../windows/accelerator-modifier-property.md) ve [türü](../windows/accelerator-type-property.md), gerekirse.  
  
6.  Tuşuna **ENTER**.  
  
    > [!NOTE]
    >  Tanımladığınız tüm Hızlandırıcıları benzersiz olduğundan emin olun. Birkaç tuş bileşimleri aynı Kimliğine sahip hiçbir olumsuz etkisi, örneğin, atanan olabilir **Ctrl** + **P** ve **F8** ID_PRINT için her ikisi de atanabilir. Ancak, birden fazla kimliği çalışmaz, örneğin, atanan bir tuş bileşimi sahip **Ctrl** + **Z** ID_SPELL_CHECK ve ID_THESAURUS atanmış.  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tablolarını düzenleme](../windows/editing-accelerator-tables.md)   
 [Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)