---
title: Cdaoındexfieldınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37149e2a4a2780c97cc7c2774c64e9a6037d37a7
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337885"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo Yapısı
`CDaoIndexFieldInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir dizin alan nesne hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 *m_strName*  
 Benzersiz dizin alanı nesnesini adlandırır. Ayrıntılar için "Name özelliği" DAO Yardım konusuna bakın.  
  
 *m_bDescending*  
 Dizin nesnesi tarafından tanımlanan sıralamaya dizini belirtir. Azalan TRUE.  
  
## <a name="remarks"></a>Açıklamalar  
 Dizin nesnesi, alanlarının üzerinde değer özelliği (veya bir tabloyu temel alan bir kayıt kümesi) dizine hangi alanları gösteren bir sayı olabilir. Bilgileri nasıl döndürülür birincil yukarıdaki başvuruları göstermek `m_pFieldInfos` üyesi bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) çağırılarak nesne `GetIndexInfo` sınıfının üye işlevinde [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Dizin nesneleri ve dizin alanı nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, DAO temel alınan MFC sınıfın nesneleri [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) dizinler koleksiyonu adlı dizin nesnelerinin bir koleksiyonu içerir. Her dizin nesnesi, alan nesnelerinin bir koleksiyonunu içerir. Bu sınıfların tek tek öğelerine dizin bilgilerinin erişmek için üye işlevleri, veya bunları tamamını tek seferde erişim bir `CDaoIndexInfo` çağırarak `GetIndexInfo` kapsayan nesnenin üye işlevi. `CDaoIndexInfo` Nesnesi daha sonra veri üyesi vardır `m_pFieldInfos`, işaret eden bir dizisi olarak `CDaoIndexFieldInfo` nesneleri.  
  
 Çağrı `GetIndexInfo` üye işlevi dizinleri koleksiyondur kapsayan nesnenin tabledef ya da kayıt depolanan ilgilendiğiniz dizin nesnesi. Ardından erişim `m_pFieldInfos` üyesi [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) nesne. Uzunluğunu `m_pFieldInfos` dizi depolanan `m_nFields`. `CDaoIndexFieldInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoIndexFieldInfo` nesne.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)

