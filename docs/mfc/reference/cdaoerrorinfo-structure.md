---
description: 'Daha fazla bilgi edinin: CDaoErrorInfo yapısı'
title: CDaoErrorInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: 3d8ae4bd133c96ef1853c8d087904c7c6eba810d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250965"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo Yapısı

`CDaoErrorInfo`Yapı, veri erişim nesneleri (DAO) için tanımlanan bir hata nesnesi hakkında bilgiler içerir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

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
Sayısal bir DAO hata kodu. DAO yardımı 'nda "Yakalanabilir veri erişim hataları" konusuna bakın.

*m_strSource*<br/>
İlk olarak hatayı oluşturan nesnenin veya uygulamanın adı. Source özelliği, ilk olarak hatayı üreten nesneyi temsil eden bir dize ifadesi belirtir; ifade genellikle nesnenin sınıf adıdır. Ayrıntılar için, DAO yardımı 'nda "kaynak özelliği" konusuna bakın.

*m_strDescription*<br/>
Bir hatayla ilişkili açıklayıcı bir dize. Ayrıntılar için, DAO yardımı 'nda "Açıklama özelliği" konusuna bakın.

*m_strHelpFile*<br/>
Bir Microsoft Windows Yardım dosyasının tam yolu. Ayrıntılar için, DAO yardımı 'nda "HelpContext, HelpFile Properties" konusuna bakın.

*m_lHelpContext*<br/>
Bir Microsoft Windows Yardım dosyasındaki konunun bağlam KIMLIĞI. Ayrıntılar için, DAO yardımı 'nda "HelpContext, HelpFile Properties" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

MFC bir sınıftaki DAO hata nesnelerini kapsüllemez. Bunun yerine, [CDaoException](../../mfc/reference/cdaoexception-class.md) sınıfı `DBEngine` , tüm çalışma alanlarını IÇEREN nesne olan DAO nesnesinde bulunan Errors koleksiyonuna erişmek için bir arabirim sağlar. Bir MFC DAO işlemi `CDaoException` yakalayacak bir nesne oluşturduğunda, MFC bir `CDaoErrorInfo` yapıyı doldurur ve özel durum nesnesinin [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) üyesinde depolar. (DAO 'YU doğrudan çağırmayı seçerseniz, doldurmanız için özel durum nesnesinin [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevini kendiniz çağırmanız gerekir `m_pErrorInfo` .)

DAO hatalarını işleme hakkında daha fazla bilgi için bkz. [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md). İlgili bilgiler için, DAO yardımı 'nda "hata nesnesi" konusuna bakın.

[CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevi tarafından alınan bilgiler bir `CDaoErrorInfo` yapıda depolanıyor. [](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) `CDaoException` Bir özel durum işleyicide yakalayacak bir nesneden m_pErrorInfo veri ÜYESINI inceleyin veya `GetErrorInfo` `CDaoException` DAO arabirimlerine doğrudan çağrı sırasında oluşmuş olabilecek hataları denetlemek için açıkça oluşturduğunuz bir nesneden çağırın. `CDaoErrorInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoErrorInfo` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException sınıfı](../../mfc/reference/cdaoexception-class.md)
