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
ms.openlocfilehash: 696d00e32ebf692d8155b93247f3ca83b0bb2b08
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Cdberrorınfo sınıfı](../../data/oledb/cdberrorinfo-class.md)