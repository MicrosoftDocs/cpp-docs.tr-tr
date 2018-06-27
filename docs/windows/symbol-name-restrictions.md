---
title: Sembol adı kısıtlamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.restrictions.name
dev_langs:
- C++
helpviewer_keywords:
- symbol names
- symbols, names
- restrictions, symbol names
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59ee6ce257609c4761e43630a66de9cb9b996269
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892341"
---
# <a name="symbol-name-restrictions"></a>Sembol Adı Kısıtlamaları
Sembol adları sınırlamalar aşağıdaki gibidir:  
  
-   Tüm [simgeleri](../windows/symbols-resource-identifiers.md) uygulama kapsamında benzersiz olmalıdır. Sembol üstbilgi dosyaları tanımlarında çakışan engeller.  
  
-   Sembol adı için geçerli karakterler, A-Z, a-z, 0-9 ve alt çizgi (_) içerir.  
  
-   Sembol adları bir rakamla başlayamaz ve 247 karakterle sınırlıdır.  
  
-   Sembol adları boşluk içeremez.  
  
-   Sembol adları büyük küçük harfe duyarlı değildir, ancak ilk simge tanım durumunun korunur. Simgeler tanımlayan üstbilgi dosyası, bir kaynak dosyasında tanımlanan kaynaklara başvurmak için kaynak derleyici/Düzenleyicisi ve C++ edinin tarafından kullanılır. Kaynak Derleyicisi/Düzenleyicisi için tek bir simge başvuran olarak hem adlar görünür C++ programı iki ayrı simge yalnızca görürsünüz durumunda, iki sembol adları için farklı.  
  
    > [!NOTE]
    >  Standart simge adı düzeni izlemeyin varsa (ID*_[keyword]) özetlenen aşağıda ve kaynak betik dosyasını oluşturmaya çalışırken kaynak kod derleyici için bilinen bir anahtar sözcük rasgele gibi görünen hatayla sonuçlanır aynı olması için simge adınızı olur Tanılama zordur oluşturma. Bunu önlemek için standart adlandırma şeması uyması.  
  
 Sembol adları kaynak ya da bunlar temsil eden nesne türünü belirtmek açıklayıcı önekleri sahip. Bu açıklayıcı önekleri metin birleşimi kimliği ile başlayın Microsoft Foundation Class Kitaplığı (MFC) aşağıdaki tabloda gösterilen simgesi adlandırma kuralları kullanır.  
  
|Kategori|önek|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|--------------|------------|---------|  
|Kaynaklar|IDR_ IDD_ IDC_ IDI_ IDB_|Hızlandırıcı veya menü (ve ilişkili ya da özel kaynaklar) iletişim kutusu imleç simgesi bit eşlem|  
|Menü öğeleri|ID_|Menü öğesi|  
|Komutlar|ID_|Komut|  
|Denetimleri ve alt pencereler|IDC_|Denetim|  
|Dizeler|IDS_|Dize tablosu dizesinde|  
|MFC|AFX_|Önceden tanımlanmış MFC sembolleri için ayrılmış|  
  

  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sembolü veya sembol adını (ID) değiştirme](../windows/changing-a-symbol-or-symbol-name-id.md)   
 [Sembol değeri kısıtlamaları](../windows/symbol-value-restrictions.md)   
 [Önceden Tanımlanmış Sembol Kimlikleri](../windows/predefined-symbol-ids.md)