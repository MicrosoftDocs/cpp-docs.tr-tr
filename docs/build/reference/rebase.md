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
ms.openlocfilehash: 4a5e2b68768b01d71532c358a14c53d8a033e1ed
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377095"
---
# <a name="rebase"></a>/REBASE
```  
/REBASE[:modifiers]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek belirtilen dosyalar için temel adresler ayarlar. EDITBIN kadar yakın 64 KB yuvarlanmasını her bir dosyanın boyutu göre bitişik adres alanındaki yeni temel adresleri atar. Temel adresler hakkında daha fazla ayrıntı için bkz: [taban adresi](../../build/reference/base-base-address.md) (/ Temel) bağlayıcı seçeneği.  
  
 Programın yürütülebilir dosyaları ve DLL'ler belirtin *dosyaları* içinde oldukları dayanmasını sırayla EDITBIN komut satırı bağımsız değişken. Bir veya daha fazla isteğe bağlı olarak belirtebilirsiniz *değiştiricileri*, her bir virgülle ayrılmış (**,**):  
  
|Değiştirici|Eylem|  
|--------------|------------|  
|TEMEL **= *** adresi*|Temel adresler dosyalara yeniden atama için bir başlangıç adresi sağlar. Belirtin *adresi* ondalık veya dil C gösterimi. TEMEL belirtilmezse varsayılan taban adresi başlangıç 0x400000 olur. Aşağı varsa kullanılan, temel belirtilmesi gerekir, ve *adresi* temel adres aralığını sonuna ayarlar.|  
|BASEFILE|COFFBASE adlı bir dosya oluşturur. Hangi bağlantının tarafından beklenen biçimde metin dosyasıdır/seçeneği temel TXT.|  
|AŞAĞI|Bitiş adresi temel adresleri aşağı atamak EDITBIN söyler. Dosyaları adres aralığı sonuna aşağıdaki olası en yüksek adresi içinde bulunan ilk dosyasını belirtilen sırada atanır. Dosyaları alma için yeterli adres alanı emin olmak için temel aşağı ile kullanılması gerekir. Belirtilen dosyaları tarafından ihtiyaç duyulan adres alanı belirlemek için EDITBIN ile /REBASE dosyalarda çalıştırmak ve görüntülenen toplam boyutu 64 KB ekleyin.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [EDITBIN Seçenekleri](../../build/reference/editbin-options.md)