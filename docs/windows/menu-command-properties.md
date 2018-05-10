---
title: Menü komut özellikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- menu items, properties
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 343c1ce255a26753c2b125d2a0a53e04808a0233
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="menu-command-properties"></a>Menü Komut Özellikleri
Aşağıdaki bilgiler görüntülenir Menüsü Özellikleri göre düzenlenmiş [Özellikler penceresini](/visualstudio/ide/reference/properties-window) seçtiğinizde menü komutu. Özellikler penceresini ayrıca, bu özellikleri görüntülemenize olanak sağlar, ancak bu kategoriye göre alfabetik olarak listelenir.  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**Sonu**|Şu değerlerden biri olabilir:<br /><br /> -   **Hiçbiri** (varsayılan): kesme yok.<br />-   **Sütun**: statik menüleri için bu değer menü komutunu yeni bir satıra yerleştirir. Açılır menüler için bu değer sütunları arasındaki hiçbir çizgi ile yeni bir sütun menü komutu yerleştirir. Bu özelliği ayarlamak menü görünümünü yalnızca çalışma zamanında, menü Düzenleyicisi'nde etkiler.<br />-   **Çubuk**: aynı sütun dışında açılır menüler için bu değer yeni bir sütun dikey çizgi eski sütunla ayırır. Bu özelliği ayarlamak menü görünümünü yalnızca çalışma zamanında, menü Düzenleyicisi'nde etkiler.|  
|**Açıklamalı alt yazı**|Menü komutu (menüsü adı) etiket metni. Aşağıdakilerden birini menü resim yazısını harflerle kısayol tuşu komutu, ve işareti ile koyun yapmak için (&).|  
|**İşaretli**|TRUE ise, menü komutu başlangıçta denetlenir. Tür: Bool. Varsayılan: False.|  
|**Etkin**|Varsa **yanlış**, menü öğesini devre dışı bırakılır.|  
|**Gri**|TRUE ise, başlangıçta gri ve etkin olmayan menü komutu. Tür: Bool. Varsayılan: False.|  
|**Yardım**|Menü öğesi sağa hizalar. Örneğin, **yardımcı** menü komutu olduğu her zaman açık tüm Windows uygulamalarını sağdaki. Bu özellik menü öğesini ayarlarsanız, bu öğeyi sağ uçta çok ile menüsünün en sonunda görüntülenir. Üst düzey öğelerine uygulanır. Varsayılan: **False**.|  
|**ID**|Üstbilgi dosyasında tanımlanan bir simge. Tür: Simge, tamsayı veya tırnak içine alınmış dize. Bile genellikle, düzenleyiciler hiçbirinde kullanılabilir herhangi bir simge kullanabilir [Özellikler penceresini](/visualstudio/ide/reference/properties-window) , seçmek aşağı açılan liste sağlamaz.|  
|**Açılan Pencere**|TRUE ise, menüsü açılır menü komuttur. Tür: Bool. Varsayılan: menü çubuğundaki en üst düzey menü True; Aksi takdirde False.|  
|**istemi**|Bu komutu vurgulanmış durum çubuğunda görüntülenecek metni içerir. Metin dizesi tablosuna menü komutu ile aynı tanımlayıcıyla yerleştirilir. Bu özellik, herhangi bir proje türü için kullanılabilir, ancak çalışma zamanında MFC belirli bir işlevdir.|  
|**Sağdan Sola Hizala**|Sağa hizalar çalışma zamanında menü çubuğundaki menü komutu. Tür: Bool. Varsayılan: False.|  
|**Sağ sol sırası**|Arabirimi sağ İbranice veya Arapça gibi sola, okuyan herhangi bir dil için yerelleştirilmiş sağdan sola görüntülemek menü komutlarını sağlar.|  
|**Ayıraç**|TRUE ise, komutu bir ayırıcı ' dir. Tür: Bool. Varsayılan: False.|  
  

  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Menü Düzenleyicisi](../windows/menu-editor.md)