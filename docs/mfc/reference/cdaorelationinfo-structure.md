---
title: Cdaorelationınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a49bdfb00c3f2ceba424af7bfdfa652cacec929e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951298"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo Yapısı
`CDaoRelationInfo` Yapısı alanları iki tablo arasında tanımlanmış bir ilişkisi hakkında bilgi içeren bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoRelationInfo  
{  
    CDaoRelationInfo();
*// Constructor  
    CString m_strName;      // Primary  
    CString m_strTable;     // Primary  
    CString m_strForeignTable;              // Primary  
    long m_lAttributes;     // Secondary  
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
    short m_nFields;        // Secondary *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 *m_strName*  
 İlişki nesnesi adlandıran. Daha fazla bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 *m_strTable*  
 İlişkinin birincil tabloda adları.  
  
 *m_strForeignTable*  
 İlişki yabancı tablosunda adları. Bir yabancı tablo yabancı anahtarlar kapsamak için kullanılmış bir tablodur. Genellikle, yabancı tablo oluşturmak veya bilgi tutarlılığı zorlamak için kullanın. Yabancı tablo genellikle bir-çok ilişkisi birçok tarafında olur. American durumları veya Kanada il ya da müşteri siparişleri kodları içeren tablolar yabancı tablolar örneklerindendir.  
  
 *m_lAttributes*  
 İlişki türü hakkında bilgi içerir. Bu üye değeri aşağıdakilerden biri olabilir:  
  
- **dbRelationUnique** birebir ilişki.  
  
- **dbRelationDontEforce'a** ilişkisi değil (hiçbir başvuru bütünlüğü) uygulanmaz.  
  
- **dbRelationInherited** ilişkisi, iki bağlı tabloları içeren noncurrent bir veritabanında yok.  
  
- **dbRelationLeft** sol birleştirme ilişkidir. Sol dış birleşim ilk kayıtların tümünü içerir (sol) iki tablonun ikinci (sağdaki) tablonun kayıtları için eşleşen değer yoksa olsa bile.  
  
- **dbRelationRight** sağ birleşim ilişkidir. Sağ dış birleştirme ikinci kayıtların tümünü içerir (sağdaki) iki tablonun ilk (sol) tablonun kayıtları için eşleşen değer yoksa olsa bile.  
  
- **dbRelationUpdateCascade** güncelleştirmeleri basamaklı.  
  
- **dbRelationDeleteCascade** silme işlemleri basamaklı.  
  
 *m_pFieldInfos*  
 Bir dizi için bir işaretçi [Cdaorelationfieldınfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) yapıları. Dizi ilişkisi içindeki her alan için bir nesne içeriyor. *M_nFields* veri üyesi dizi öğelerinin sayısını verir.  
  
 *M_nFields*  
 Sayısı `CDaoRelationFieldInfo` nesnelerini *m_pFieldInfos* veri üyesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Birincil ve ikincil yukarıdaki başvuruları nasıl bilgileri tarafından döndürülen belirtmek [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) üye işlevi sınıfında `CDaoDatabase`.  
  
 İlişki nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, bir MFC nesnesinin temelindeki DAO nesne `CDaoDatabase` sınıfı ilişkisi nesneler koleksiyonunu korur: `CDaoDatabase` ilişkisi bilgileri ya da, bazı tek tek öğelere erişmek için kaynakları üye işlevleri erişebilmeniz tümünü bir defada bir ile`CDaoRelationInfo` çağırarak nesne `GetRelationInfo` içeren veritabanı nesnesinin üye işlevi.  
  
 Tarafından alınan bilgileri [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) üye işlevi depolanır bir `CDaoRelationInfo` yapısı. `CDaoRelationInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoRelationInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDaoRelationFieldInfo Yapısı](../../mfc/reference/cdaorelationfieldinfo-structure.md)
