---
title: CDaoErrorInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoErrorInfo
helpviewer_keywords:
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
ms.openlocfilehash: a7b273bd2aa6b428bf795c1842455b8bfe187cc8
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096145"
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo Yapısı

Yapı `CDaoErrorInfo` , veri erişim nesneleri (DAO) için tanımlanan bir hata nesnesi hakkında bilgiler içerir.
DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.


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

MFC bir sınıftaki DAO hata nesnelerini kapsüllemez. Bunun yerine, [CDaoException](../../mfc/reference/cdaoexception-class.md) sınıfı, tüm çalışma alanlarını içeren nesne olan DAO `DBEngine` nesnesinde bulunan Errors koleksiyonuna erişmek için bir arabirim sağlar. Bir MFC DAO işlemi yakalayacak bir `CDaoException` nesne oluşturduğunda, MFC bir `CDaoErrorInfo` yapıyı doldurur ve özel durum nesnesinin [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) üyesinde depolar. (DAO 'YU doğrudan çağırmayı seçerseniz, doldurmanız `m_pErrorInfo`için özel durum nesnesinin [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevini kendiniz çağırmanız gerekir.)

DAO hatalarını işleme hakkında daha fazla bilgi için bkz. Makale [özel durumları: Veritabanı özel](../../mfc/exceptions-database-exceptions.md)durumları. İlgili bilgiler için, DAO yardımı 'nda "hata nesnesi" konusuna bakın.

[CDaoException:: GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevi tarafından alınan bilgiler bir `CDaoErrorInfo` yapıda depolanıyor. Özel durum [](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) işleyicisinde yakalayacak bir `CDaoException` nesneden m_pErrorInfo veri üyesini inceleyin veya doğrudan çağrı sırasında oluşmuş olabilecek hataları `GetErrorInfo` denetlemek için `CDaoException` açıkça oluşturduğunuz bir nesneden çağırın DAO arabirimlerine. `CDaoErrorInfo`Ayrıca, hata `Dump` ayıklama yapılarında bir üye işlevi tanımlar. `Dump` Bir`CDaoErrorInfo` nesnenin içeriğini dökmek için kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
