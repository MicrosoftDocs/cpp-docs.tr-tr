---
title: CDaoParameterInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 62addd44f8aa8fceafef6a27244994a2ec6b766b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399791"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo Yapısı

`CDaoParameterInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir parametre nesnesi hakkında bilgiler içerir.

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

*m_strName*<br/>
Parametre nesnesine adlandıran. Daha fazla bilgi için "Name özelliği" DAO Yardım konusuna bakın.

*m_nType*<br/>
Bir parametre nesnesi veri türünü gösteren bir değer. Olası değerler listesi için bkz. *m_nType* üyesi [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Daha fazla bilgi için DAO Yardımı'nda "Type özelliği" konusuna bakın.

*m_varValue*<br/>
Depolanan parametrenin değeri bir [COleVariant](../../mfc/reference/colevariant-class.md) nesne.

## <a name="remarks"></a>Açıklamalar

Birincil ve ikincil yukarıdaki başvuruları nasıl bilgileri tarafından döndürülen belirtmek [Getparameterınfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) sınıf üyesi işlevinde `CDaoQueryDef`.

MFC DAO parametresi nesnelerini bir sınıftaki kapsamayan. Temel alınan MFC DAO querydef nesneleri `CDaoQueryDef` kendi parametrelerini koleksiyonlarında nesneleri depolamak parametreleri. Parametre nesneleri erişmek için bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesne, querydef nesnesinin çağrı `GetParameterInfo` belirli bir parametre veya parametreler koleksiyonunu bir dizine üye işlevi. Kullanabileceğiniz [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) üye işlevi ile birlikte `GetParameterInfo` parametreleri toplulukta döngü.

Tarafından alınan bilgileri [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi depolanan bir `CDaoParameterInfo` yapısı. Çağrı `GetParameterInfo` parametre nesnesi, parametre koleksiyonunda depolanan QueryDefs için.

> [!NOTE]
>  İsterseniz almak veya yalnızca bir parametre değerini ayarlamak için kullanın [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) ve [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) sınıfın üye işlevleri `CDaoRecordset`.

`CDaoParameterInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoParameterInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)
