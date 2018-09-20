---
title: Cdaoerrorınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b576398d2d6166682bd897b63123a8c8388864d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419574"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo Yapısı

`CDaoErrorInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir hata nesnesi hakkında bilgiler içerir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoErrorInfo
{
    long m_lErrorCode;
    CString m_strSource;
    CString m_strDescription;
    CString m_strHelpFile;
    long m_lHelpContext;
};
```

#### <a name="parameters"></a>Parametreler

*m_lErrorCode*<br/>
Sayısal DAO hata kodu. "Yakalanabilir veri erişimi hatası" DAO Yardım konusuna bakın.

*m_strSource*<br/>
Nesne ya da ilk olarak hatayı oluşturan uygulamanın adı. Source özelliği ilk olarak hatayı oluşturan nesnesini temsil eden bir dize ifadesi belirtir; ifade genellikle nesnenin sınıf adıdır. Ayrıntılar için DAO Yardımı'nda "kaynak özelliği" konusuna bakın.

*m_strDescription*<br/>
Bir hatayla ilişkili açıklayıcı bir dize. Ayrıntılar için "Description özelliği" DAO Yardım konusuna bakın.

*m_strHelpFile*<br/>
Bir Microsoft Windows Yardım dosyasının tam yolu. Ayrıntılar için DAO Yardımı'ndaki "HelpContext HelpFile özellikleri" bölümüne bakın.

*m_lHelpContext*<br/>
Microsoft Windows Yardım dosyasındaki bir konu için bir bağlam kimliği. Ayrıntılar için DAO Yardımı'ndaki "HelpContext HelpFile özellikleri" bölümüne bakın.

## <a name="remarks"></a>Açıklamalar

MFC DAO hata nesneleri bir sınıftaki kapsamayan. Bunun yerine, [CDaoException](../../mfc/reference/cdaoexception-class.md) sınıfı DAO'da bulunan hatalar koleksiyonuna erişmek için bir arabirim sağlayan `DBEngine` nesnesi, ayrıca tüm çalışma alanlarını içeren nesne. Ne zaman bir MFC DAO işlemi oluşturur bir `CDaoException` nesne, catch, MFC dolduran bir `CDaoErrorInfo` yapısı ve özel durum nesne depolar [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) üyesi. (DAO doğrudan çağırmak tercih ederseniz özel durum nesnenin çağırmalıdır [Geterrorınfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevi doldurmak için kendiniz `m_pErrorInfo`.)

DAO hataları işleme hakkında daha fazla bilgi için bkz [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md). İlgili bilgiler için DAO Yardımı'nda "hata nesnesi" konusuna bakın.

Tarafından alınan bilgileri [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevi depolanan bir `CDaoErrorInfo` yapısı. İnceleme [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) veri üyesi bir `CDaoException` bir özel durum işleyicisi veya çağrı catch nesne `GetErrorInfo` gelen bir `CDaoException` olabilecek hataları denetlemek için oluşturduğunuz nesnesi DAO arabirimler doğrudan çağrı sırasında oluştu. `CDaoErrorInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoErrorInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
