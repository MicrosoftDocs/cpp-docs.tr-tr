---
title: -REBASE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /rebase
dev_langs:
- C++
helpviewer_keywords:
- base addresses [C++]
- -REBASE editbin option
- REBASE editbin option
- DLLs [C++], linking
- executable files [C++], base address
- /REBASE editbin option [C++]
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 686306316e6950ba62ea7c44522b95f4d935be0b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216180"
---
# <a name="rebase"></a>/REBASE
```  
/REBASE[:modifiers]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek, belirtilen dosyalar için temel adres ayarlar. EDITBIN yakın 64 KB'lık kadar yuvarlanır her dosyasının boyutuna göre bitişik bir adres alanında yeni temel adresleri de atar. Temel adresler hakkında daha fazla ayrıntı için bkz: [temel adres](../../build/reference/base-base-address.md) (/ BASE) bağlayıcı seçeneği.  
  
 Programın yürütülebilir dosyaları ve dll belirtin *dosyaları* oldukları almasını sırada EDITBIN komut satırı bağımsız değişkeni. İsteğe bağlı olarak bir veya daha fazla belirtebilirsiniz *değiştiriciler*her bir virgülle ayrılmış (**,**):  
  
|Değiştirici|Eylem|  
|--------------|------------|  
|**TEMEL =**<em>adresi</em>|Başlangıç adresini temel adresler dosyalarının yeniden atama için sağlar. Belirtin *adresi* ondalık ya da C dili gösterimi. TEMEL belirtilmezse, başlangıç temel adresi 0x400000 varsayılandır. AŞAĞI, kullanılan temel belirtilmelidir ve *adresi* temel adresler aralığının sonuna ayarlar.|  
|**BASEFILE**|COFFBASE adlı bir dosya oluşturur. Bir metin dosyasıdır bağlantının tarafından beklenen biçimde/temel seçeneği, TXT.|  
|**AŞAĞI**|Bitiş adresi temel adresleri aşağı doğru atamak EDITBIN söyler. Dosyalar, en yüksek olası adresi adres aralığının sonunu aşağıda bulunan ilk dosyasını belirtilen sırada atanır. Dosyaları alma için yeterli adres alanına emin olmak için temel aşağı ile kullanılması gerekir. Tarafından belirtilen dosyalarını gereken adres alanını belirlemek için EDITBIN /REBASE ile dosyalarda çalıştırmak ve için görüntülenen toplam boyutu 64 KB ekleyin.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN Seçenekleri](../../build/reference/editbin-options.md)