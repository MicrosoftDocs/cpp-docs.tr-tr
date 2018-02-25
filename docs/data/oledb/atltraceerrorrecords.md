---
title: AtlTraceErrorRecords | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 024a4331b71b3414aa7d83f27ecaca4e5d2f11de
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
Bir hata döndürülürse, OLE DB hata kaydı bilgi döküm aygıta dökümünü yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hErr`  
 [in] Bir `HRESULT` bir OLE DB tüketici şablonu üye işlevi tarafından döndürülen.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `hErr` değil `S_OK`, `AtlTraceErrorRecords` OLE DB hata kaydı bilgi döküm aygıta dökümleri ( **hata ayıklama** çıktı penceresi veya bir dosya sekmesinde). Sağlayıcısı'ndan alınan, hata kaydı bilgileri, her hata kayıt girişi için satır numarası, kaynak, açıklama, Yardım dosyası, içerik ve GUID içerir. `AtlTraceErrorRecords` Bu bilgileri yalnızca hata ayıklama yapıları dökümünü yapar. Yayın derlemelerde çıkışı iyileştirilmiş bir boş stub'dır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo Sınıfı](../../data/oledb/cdberrorinfo-class.md)