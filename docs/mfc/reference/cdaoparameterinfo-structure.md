---
title: "Cdaoparameterınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDaoParameterInfo
dev_langs: C++
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3aabdb1dd59e1039f81d2ffe75c0d9e0770e43db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo Yapısı
`CDaoParameterInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan bir parametre nesne hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoParameterInfo  
{  
    CString m_strName;       // Primary  
    short m_nType;           // Primary  
    ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `m_strName`  
 Parametre nesnesi adlandıran. Daha fazla bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 `m_nType`  
 Bir parametre nesnesinin veri türünü belirten bir değer. Olası değerler listesi için bkz: `m_nType` üyesi [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Daha fazla bilgi için DAO Yardımı'ndaki "Type özelliği" konusuna bakın.  
  
 *m_varValue*  
 Depolanan parametrenin değeri bir [COleVariant](../../mfc/reference/colevariant-class.md) nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Birincil ve ikincil yukarıdaki başvuruları nasıl bilgileri tarafından döndürülen belirtmek [Getparameterınfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi sınıfında `CDaoQueryDef`.  
  
 MFC DAO parametre nesneleri bir sınıftaki kapsülleyen değil. DAO querydef nesneleri temel alınan MFC `CDaoQueryDef` kendi parametreleri koleksiyonlarda nesneleri depolamak parametreleri. Parametre nesnelere erişmek için bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesne, querydef nesnesinin çağrı `GetParameterInfo` belirli parametre adı veya dizin parametre koleksiyonuna üye işlevi. Kullanabileceğiniz [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) üye işlevi ile birlikte `GetParameterInfo` parametreleri toplulukta döngü.  
  
 Tarafından alınan bilgileri [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi depolanır bir `CDaoParameterInfo` yapısı. Çağrı `GetParameterInfo` parametre nesnesi, parametreleri koleksiyonda depolanan querydef nesnesi için.  
  
> [!NOTE]
>  Almak veya yalnızca bir parametre değerini ayarlamak için kullanmak istiyorsanız, [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) ve [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) sınıfının üye işlevleri `CDaoRecordset`.  
  
 `CDaoParameterInfo`Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoParameterInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)
