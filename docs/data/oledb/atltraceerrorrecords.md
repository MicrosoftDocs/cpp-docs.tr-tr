---
title: AtlTraceErrorRecords | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs: C++
helpviewer_keywords: AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a3f8542f2c897f45916ac62fbac147259b2362d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
Bir hata döndürülürse, OLE DB hata kaydı bilgi döküm aygıta dökümünü yapar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      inline void AtlTraceErrorRecords(   
   HRESULT hrErr = S_OK    
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hErr`  
 [in] Bir `HRESULT` bir OLE DB tüketici şablonu üye işlevi tarafından döndürülen.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `hErr` değil `S_OK`, `AtlTraceErrorRecords` OLE DB hata kaydı bilgi döküm aygıta dökümleri ( **hata ayıklama** çıktı penceresi veya bir dosya sekmesinde). Sağlayıcısı'ndan alınan, hata kaydı bilgileri, her hata kayıt girişi için satır numarası, kaynak, açıklama, Yardım dosyası, içerik ve GUID içerir. `AtlTraceErrorRecords`Bu bilgileri yalnızca hata ayıklama yapıları dökümünü yapar. Yayın derlemelerde çıkışı iyileştirilmiş bir boş stub'dır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo Sınıfı](../../data/oledb/cdberrorinfo-class.md)