---
title: Sınıf Oluşturucular ve Lisanslama
ms.date: 11/04/2016
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: e3fed6520cdbe0fd964e4e80e7c9ed9b78296d16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372305"
---
# <a name="class-factories-and-licensing"></a>Sınıf Oluşturucular ve Lisanslama

OLE denetiminizin bir örneğini oluşturmak için, bir kapsayıcı uygulaması denetimin sınıf fabrikasının bir üye işlevini çağırır. Denetiminiz gerçek bir OLE nesnesi olduğundan, sınıf fabrikası denetiminizin örneklerini oluşturmaktan sorumludur. Her OLE kontrol sınıfının bir sınıf fabrikası olmalıdır.

OLE denetimlerinin bir diğer önemli özelliği de lisans uygulama yetenekleridir. ControlWizard, denetim projenizin oluşturulması sırasında lisanslama yı dahil etmenizi sağlar. Denetim lisanslama hakkında daha fazla bilgi için [ActiveX Denetimleri makalesine bakın: ActiveX Denetimi Lisanslama.](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)

Aşağıdaki tablo, denetiminizin sınıf fabrikasını bildirmek ve uygulamak ve denetiminizi lisanslamak için kullanılan çeşitli makroları ve işlevleri listeler.

### <a name="class-factories-and-licensing"></a>Sınıf Oluşturucular ve Lisanslama

|||
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|Sınıf fabrikasını OLE denetimi veya özellik sayfası olarak bildirir.|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Denetimişlevini `GetClassID` uygular ve sınıf fabrikasının bir örneğini bildirir.|
|[BEGIN_OLEFACTORY](#begin_olefactory)|Herhangi bir lisans işlevlerinin bildirimini başlatın.|
|[END_OLEFACTORY](#end_olefactory)|Herhangi bir lisans işlevlerinin bildirimini sona erdirer.|
|[AfxVerifyLicFile](#afxverifylicfile)|Denetimin belirli bir bilgisayarda kullanılmak üzere lisanslı olup olmadığını doğrular.|

## <a name="declare_olecreate_ex"></a><a name="declare_olecreate_ex"></a>DECLARE_OLECREATE_EX

Bir sınıf fabrikasını `GetClassID` ve denetim sınıfınızın üye işlevini bildirir.

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Kontrol sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Lisanslamayı desteklemeyen bir denetim için bu makroyu denetim sınıfı üstbilgi dosyasında kullanın.

Bu makronun aşağıdaki kod örneğiyle aynı amaca hizmet ettiğini unutmayın:

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="implement_olecreate_ex"></a><a name="implement_olecreate_ex"></a>IMPLEMENT_OLECREATE_EX

Denetiminizin sınıf fabrikasını ve denetim sınıfınızın [GetClassID](../../mfc/reference/colecontrol-class.md#getclassid) üye işlevini uygular.

```
IMPLEMENT_OLECREATE_EX(
   class_name,
    external_name,
    l,
    w1,
    w2,
    b1,
    b2,
    b3,
    b4,
    b5,
    b6,
    b7,
    b8)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Denetim özelliği sayfası sınıfının adı.

*external_name*<br/>
Uygulamalara maruz kalan nesne adı.

*l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8*<br/>
Sınıfın CLSID bileşenleri. Bu parametreler hakkında daha fazla bilgi [için, IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate)için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Bu makro, DECLARE_OLECREATE_EX makroyu veya BEGIN_OLEFACTORY ve END_OLEFACTORY makrolarını kullanan herhangi bir denetim sınıfı için uygulama dosyasında görünmelidir. Dış ad, diğer uygulamalara maruz kalan OLE denetiminin tanımlayıcısýdýr. Kapsayıcılar bu denetim sınıfının bir nesnesini istemek için bu adı kullanır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="begin_olefactory"></a><a name="begin_olefactory"></a>BEGIN_OLEFACTORY

Denetim sınıfınızın üstbilgi dosyasında sınıf fabrikanızın bildirimibaşlar.

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıf fabrikası bu olan denetim sınıfının adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıf fabrika lisanslama işlevlerinin bildirimleri BEGIN_OLEFACTORY hemen sonra başlamalıdır.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="end_olefactory"></a><a name="end_olefactory"></a>END_OLEFACTORY

Kontrolünüzün sınıf fabrikasının bildirimisona erer.

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıf fabrikası bu olan kontrol sınıfının adı.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="afxverifylicfile"></a><a name="afxverifylicfile"></a>AfxVerifyLicFile

Adlandırılmış lisans dosyasının OLE `pszLicFileName` denetimi için geçerli olduğunu doğrulamak için bu işlevi arayın.

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>Parametreler

*Hınstance*<br/>
Lisanslı denetimle ilişkili DLL'nin örnek tutamacı.

*pszLicFileName*<br/>
Lisans dosya adını içeren geçersiz sonlandırılmış karakter dizesini işaret eder.

*pszLicFileContents*<br/>
Lisans dosyasının başında bulunan sırayla eşleşmesi gereken bir bayt sırasına işaret eder.

*Cch*<br/>
*pszLicFileContents*karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Lisans dosyası varsa ve *pszLicFileContents*karakter dizisi ile başlar Sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*Cch* -1 ise, bu işlev kullanır:

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxctl.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
