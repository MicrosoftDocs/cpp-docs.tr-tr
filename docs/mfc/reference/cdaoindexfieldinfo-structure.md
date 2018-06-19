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
ms.openlocfilehash: 7be9a6a9db842f1e80be62f48a9990cff36168e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367262"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo Yapısı
`CDaoIndexFieldInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan bir dizin alan nesne hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `m_strName`  
 Dizin alanı nesneyi benzersiz olarak adlandırır. Ayrıntılar için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 *m_bDescending*  
 Dizin nesnesi tarafından tanımlanan dizin sıralama gösterir. **DOĞRU** azalan durumunda.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir dizin nesnesi üzerinde bir tabledef (veya bir tabloya dayalı bir kayıt kümesi) dizine hangi alanların gösteren alanları, bir dizi sahip olabilir. Bilgilerin nasıl döndürülür birincil yukarıdaki başvuruları belirtmek `m_pFieldInfos` üyesi bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) çağırılarak alınır nesne `GetIndexInfo` sınıfının üye işlevini [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Dizin ve dizin alanı nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, DAO temel MFC sınıfının nesneleri [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) dizinler koleksiyonu adlı dizin nesnelerinin bir koleksiyonu içerir. Her dizin nesnesi, buna karşılık, alan nesneler koleksiyonunu içerir. Bu sınıfların dizin bilgilerinin tek tek öğelere erişmek için üye işlevleri sağlamak ya da bunları tamamını tek seferde erişebilirsiniz bir `CDaoIndexInfo` çağırarak nesne `GetIndexInfo` kapsayan nesnenin üye işlevi. `CDaoIndexInfo` Nesnesi, daha sonra bir veri üyeye sahip `m_pFieldInfos`, işaret eden bir dizi için `CDaoIndexFieldInfo` nesneleri.  
  
 Çağrı `GetIndexInfo` dizinleri içinde koleksiyonu içeren tabledef veya kayıt kümesi nesnesi üye işlevini depolanan ilgilendiğiniz dizin nesnesi. Sonra erişim `m_pFieldInfos` üyesi [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) nesnesi. Uzunluğu `m_pFieldInfos` dizi depolanır `m_nFields`. `CDaoIndexFieldInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoIndexFieldInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)

