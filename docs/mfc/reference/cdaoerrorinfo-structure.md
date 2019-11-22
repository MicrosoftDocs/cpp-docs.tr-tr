---
title: CDaoErrorInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: 8d731c8e8bea1adc850ab3c00c7688b9f8c9b819
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304232"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo Yapısı

`CDaoErrorInfo` yapısı, veri erişim nesneleri (DAO) için tanımlanan bir hata nesnesi hakkında bilgi içerir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

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

MFC bir sınıftaki DAO hata nesnelerini kapsüllemez. Bunun yerine, [CDaoException](../../mfc/reference/cdaoexception-class.md) sınıfı, DAO `DBEngine` nesnesinde bulunan hatalar koleksiyonuna erişmek için bir arabirim sağlar. bu nesne, tüm çalışma alanlarını da içerir. Bir MFC DAO işlemi yakalayacak bir `CDaoException` nesnesi oluşturduğunda, MFC bir `CDaoErrorInfo` yapısını doldurur ve özel durum nesnesinin [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) üyesinde depolar. (DAO 'YU doğrudan çağırmayı seçerseniz, `m_pErrorInfo`doldurmanız için özel durum nesnesinin [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevini kendiniz çağırmanız gerekir.)

DAO hatalarını işleme hakkında daha fazla bilgi için bkz. [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md). İlgili bilgiler için, DAO yardımı 'nda "hata nesnesi" konusuna bakın.

[CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevi tarafından alınan bilgiler `CDaoErrorInfo` bir yapıda depolanıyor. Bir özel durum işleyicide yakalayadığınız bir `CDaoException` nesnesinden [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) veri üyesini ınceleyın veya DAO arabirimlerine doğrudan çağrı sırasında oluşmuş olabilecek hataları denetlemek için açıkça oluşturduğunuz bir `CDaoException` nesnesinden `GetErrorInfo` çağırın. `CDaoErrorInfo` Ayrıca hata ayıklama yapılarında bir `Dump` member işlevi tanımlar. Bir `CDaoErrorInfo` nesnesinin içeriğini dökmek için `Dump` kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
