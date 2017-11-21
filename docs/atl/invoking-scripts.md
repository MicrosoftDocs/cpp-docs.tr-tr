---
title: "Komut dosyaları (ATL) çağırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StringRegister
dev_langs: C++
helpviewer_keywords:
- StringRegister method
- scripts, invoking registry in ATL
ms.assetid: eabd41ee-586b-4266-9e92-5aaad04b73a4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c1fc6893b02dccff6bb30d7a20d1a2c1dce9fbb1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="invoking-scripts"></a>Komut dosyaları çağırma
[Değiştirilebilir parametreler (kayıt şirketinizin önişlemci) kullanarak](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) değiştirme eşlemeleri açıklanır ve kayıt yöntemi değinmektedir **AddReplacement**. Sekiz diğer yöntemleri komut belirli kayıt şirketi var ve tüm aşağıdaki tabloda açıklanmıştır.  
  
|Yöntem|Sözdizimi/açıklama|  
|------------|-------------------------|  
|**ResourceRegister**|**HRESULT ResourceRegister (LPCOLESTR***resFileName* **, UINT** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> Bir modülün kaynağında bulunan komut dosyası kaydeder. *resFileName* modülü UNC yolunu gösterir. `nID`ve `szType` kaynağın kimliği ve türü, sırasıyla içerir.|  
|**ResourceUnregister**|**HRESULT ResourceUnregister (LPCOLESTR***resFileName* **, UINT** `nID` **, LPCOLESTR** `szType` **);** <br /><br /> Bir modülün kaynağında bulunan betik kaydını siler. *resFileName* modülü UNC yolunu gösterir. `nID`ve `szType` kaynağın kimliği ve türü, sırasıyla içerir.|  
|**ResourceRegisterSz**|**HRESULT ResourceRegisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);** <br /><br /> Bir modülün kaynağında bulunan komut dosyası kaydeder. *resFileName* modülü UNC yolunu gösterir. *szID* ve `szType` kaynağın dize tanımlayıcı ve türü, sırasıyla içerir.|  
|**ResourceUnregisterSz**|**HRESULT ResourceUnregisterSz (LPCOLESTR***resFileName* **, LPCOLESTR***szID* **, LPCOLESTR** `szType` **);** <br /><br /> Bir modülün kaynağında bulunan betik kaydını siler. *resFileName* modülü UNC yolunu gösterir. *szID* ve `szType` kaynağın dize tanımlayıcı ve türü, sırasıyla içerir.|  
|**FileRegister**|**HRESULT FileRegister (LPCOLESTR***fileName***);** <br /><br /> Komut dosyasını bir dosyaya kaydeder. *fileName* içeriyor (veya) kaynak komut dosyası bir dosya bir UNC yoludur.|  
|**FileUnregister**|**HRESULT FileUnregister (LPCOLESTR***fileName***);** <br /><br /> Komut dosyasında kaydını siler. *fileName* içeriyor (veya) kaynak komut dosyası bir dosya bir UNC yoludur.|  
|**StringRegister**|**HRESULT StringRegister (LPCOLESTR***veri***);** <br /><br /> Kodun bir dize kaydeder. *veri* komut dosyasının kendisini içerir.|  
|**StringUnregister**|**HRESULT StringUnregister (LPCOLESTR***veri***);** <br /><br /> Bir dize betik kaydını siler. *veri* komut dosyasının kendisini içerir.|  
  
 **ResourceRegisterSz** ve **ResourceUnregisterSz**, benzer **ResourceRegister** ve **ResourceUnregister**, ancak belirtmenize olanak veren bir dize tanımlayıcısı.  
  
 Yöntemleri **FileRegister** ve **FileUnregister** bir kaynak betik istemiyorsanız veya kendi dosyasındaki komut dosyasının çalışmasını istiyorsanız kullanışlıdır. Yöntemleri **StringRegister** ve **StringUnregister** dinamik olarak ayrılan dizesinde depolanması .rgs dosya izin verin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)

