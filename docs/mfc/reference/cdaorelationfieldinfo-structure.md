---
title: Cdaorelationfieldınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRelationFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e53daaaa5ef4997762342cbfb74ae4d5fa96097d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo Yapısı
`CDaoRelationFieldInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir ilişkisi alanında hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoRelationFieldInfo  
{  
    CString m_strName;           // Primary  
    CString m_strForeignName;    // Primary  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `m_strName`  
 İlişkinin birincil tablodaki alanının adı.  
  
 `m_strForeignName`  
 İlişkinin yabancı tablosundaki alanının adı.  
  
## <a name="remarks"></a>Açıklamalar  
 DAO ilişkisi nesne alanları birincil tablo ve bu ilişkiyi tanımlayan yabancı bir tabloda alanlar belirtir. Yukarıdaki yapısı tanımında birincil başvuruları bilgileri nasıl döndürülür belirtmek `m_pFieldInfos` üyesi bir [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) çağırılarak alınır nesne [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)sınıfının üye işlevini `CDaoDatabase`.  
  
 İlişki ve ilişkisi alan nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, DAO temel MFC sınıfının nesneleri [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) ilişkiler koleksiyonu adlı ilişkisi nesnelerinin bir koleksiyonu içerir. Her ilişki nesnesi, sırasıyla ilişkisi alan nesneler koleksiyonunu içerir. Her ilişkisi alan nesne yabancı tablosundaki bir alanla birincil tablo alanına hatalarla ilintilidir. Birlikte ele alındığında, ilişki alan nesneleri grubu alanlarının her tabloda birlikte bu ilişkiyi tanımlayan tanımlayın. `CDaoDatabase` İlişki nesneleriyle erişim sağlar bir `CDaoRelationInfo` çağırarak nesne `GetRelationInfo` üye işlevi. `CDaoRelationInfo` Nesnesi, daha sonra bir veri üyeye sahip `m_pFieldInfos`, işaret eden bir dizi için `CDaoRelationFieldInfo` nesneleri.  
  
 Çağrı [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) içeren üye işlevi `CDaoDatabase` nesne ilgilendiğiniz ilişkisi nesne koleksiyonu ilişkileri depolanır özelliği. Sonra erişim `m_pFieldInfos` üyesi [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesi. `CDaoRelationFieldInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoRelationFieldInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo Yapısı](../../mfc/reference/cdaorelationinfo-structure.md)
