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
ms.openlocfilehash: 4c11ebaa7d315d09cea40b4ddc94d5afff498bf7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo Yapısı
`CDaoErrorInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir hata nesne hakkında bilgiler içerir.  
  
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
 *m_lErrorCode*  
 Sayısal bir DAO hata kodu. "Yakalanabilir veri erişimi hatası" DAO Yardım konusuna bakın.  
  
 *m_strSource*  
 Nesnenin veya başlangıçta hatayı oluşturan uygulamanın adı. Source özelliği ilk olarak hatayı oluşturan nesnesini temsil eden bir dize ifadesi belirtir; genellikle nesnenin sınıf adı ifadesidir. Ayrıntılar için DAO Yardımı'ndaki "kaynak özelliği" konusuna bakın.  
  
 *m_strDescription*  
 Bir hata ile ilişkili açıklayıcı bir dize. Ayrıntılar için DAO Yardımı'ndaki "açıklama özellik" konusuna bakın.  
  
 *m_strHelpFile*  
 Microsoft Windows Yardım dosyasının tam yolu. Ayrıntılar için DAO Yardımı'ndaki "HelpContext, HelpFile özellikleri" konusuna bakın.  
  
 *m_lHelpContext*  
 Microsoft Windows Yardım dosyasındaki bir konu için bir bağlam kimliği. Ayrıntılar için DAO Yardımı'ndaki "HelpContext, HelpFile özellikleri" konusuna bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 MFC DAO hata nesneleri bir sınıftaki kapsülleyen değil. Bunun yerine, [CDaoException](../../mfc/reference/cdaoexception-class.md) sınıfı DAO'da bulunan hatalar koleksiyonuna erişmek için bir arabirim sağlayan **DBEngine** nesnesi, ayrıca tüm çalışma alanları içeren nesne. Ne zaman bir MFC DAO işlem oluşturur bir `CDaoException` nesne, yakalama, MFC doldurur bir `CDaoErrorInfo` yapısı ve özel durum nesne depolar [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) üyesi. (Doğrudan çağırmak seçerseniz, özel durum nesnenin çağırmalısınız [Geterrorınfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevi kendiniz doldurmak için `m_pErrorInfo`.)  
  
 DAO hataları işleme hakkında daha fazla bilgi için bkz: [özel durumlar: veritabanı özel durumları](../../mfc/exceptions-database-exceptions.md). İlgili bilgi için DAO Yardımı'ndaki "hata nesnesi" konusuna bakın.  
  
 Tarafından alınan bilgileri [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) üye işlevi depolanır bir `CDaoErrorInfo` yapısı. İncelemek [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) veri üyesi bir `CDaoException` bir özel durum işleyici veya çağrı catch nesne `GetErrorInfo` gelen bir `CDaoException` olabilecek hataları denetlemek için oluşturduğunuz nesnesi DAO arabirimleri için doğrudan çağrısı sırasında oluştu. `CDaoErrorInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoErrorInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
