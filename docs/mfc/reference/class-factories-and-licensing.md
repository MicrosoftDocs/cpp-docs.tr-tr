---
description: 'Daha fazla bilgi edinin: sınıf fabrikaları ve lisanslama'
title: Sınıf Oluşturucular ve Lisanslama
ms.date: 11/04/2016
helpviewer_keywords:
- class factories [MFC], and licensing
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
ms.openlocfilehash: 7470a5828df358a28db5a30832f98314e09a133e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236847"
---
# <a name="class-factories-and-licensing"></a>Sınıf Oluşturucular ve Lisanslama

OLE denetiminizin bir örneğini oluşturmak için bir kapsayıcı uygulaması, denetimin sınıf fabrikasının üye işlevini çağırır. Denetiminiz gerçek bir OLE nesnesi olduğundan, bir sınıf fabrikası denetiminizin örneklerini oluşturmaktan sorumludur. Her OLE denetim sınıfının bir sınıf fabrikası olmalıdır.

OLE denetimlerinin başka bir önemli özelliği de lisans zorlayabilme yeteneğidir. ControlWizard, denetim projenizin oluşturulması sırasında lisanslama eklemenize olanak tanır. Denetim lisanslama hakkında daha fazla bilgi için bkz. [ActiveX denetimleri: ActiveX denetimini lisanslama](../../mfc/mfc-activex-controls-licensing-an-activex-control.md).

Aşağıdaki tabloda, denetiminizin sınıf fabrikasını bildirmek ve uygulamak ve denetiminizin lisanslamak için kullanılan çeşitli makrolar ve işlevler listelenmektedir.

### <a name="class-factories-and-licensing"></a>Sınıf Oluşturucular ve Lisanslama

|Makro veya işlev|Açıklama|
|-|-|
|[DECLARE_OLECREATE_EX](#declare_olecreate_ex)|OLE denetimi veya özellik sayfası için sınıf fabrikası bildirir.|
|[IMPLEMENT_OLECREATE_EX](#implement_olecreate_ex)|Denetimin `GetClassID` işlevini uygular ve sınıf fabrikasının bir örneğini bildirir.|
|[BEGIN_OLEFACTORY](#begin_olefactory)|Herhangi bir lisans işlevinin bildirimini başlatır.|
|[END_OLEFACTORY](#end_olefactory)|Herhangi bir lisans işlevinin bildirimini sonlandırır.|
|[AfxVerifyLicFile](#afxverifylicfile)|Bir denetimin belirli bir bilgisayarda kullanım için lisanslanmış olup olmadığını doğrular.|

## <a name="declare_olecreate_ex"></a><a name="declare_olecreate_ex"></a> DECLARE_OLECREATE_EX

Bir sınıf fabrikası ve `GetClassID` denetim sınıfınızın üye işlevini bildirir.

```
DECLARE_OLECREATE_EX(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Denetim sınıfının adı.

### <a name="remarks"></a>Açıklamalar

Bu makroyu, lisansı desteklemeyen bir denetim için denetim sınıfı üstbilgi dosyasında kullanın.

Bu makronun aşağıdaki kod örneğiyle aynı amaca hizmet ettiği unutulmamalıdır:

[!code-cpp[NVC_MFCAxCtl#14](../../mfc/reference/codesnippet/cpp/class-factories-and-licensing_1.h)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="implement_olecreate_ex"></a><a name="implement_olecreate_ex"></a> IMPLEMENT_OLECREATE_EX

Denetim sınıfınızın, denetimin sınıf fabrikasını ve [Getclassid](../../mfc/reference/colecontrol-class.md#getclassid) üye işlevini uygular.

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
Denetim özelliği sayfa sınıfının adı.

*external_name*<br/>
Uygulamalara sunulan nesne adı.

*l, W1, W2, B1, B2, B3, B4, B5, B6, B7, B8*<br/>
Sınıfın CLSID 'SI. Bu parametreler hakkında daha fazla bilgi için bkz. [IMPLEMENT_OLECREATE](run-time-object-model-services.md#implement_olecreate)açıklamaları.

### <a name="remarks"></a>Açıklamalar

Bu makro, DECLARE_OLECREATE_EX makrosunu veya BEGIN_OLEFACTORY ve END_OLEFACTORY makrolarını kullanan herhangi bir denetim sınıfı için uygulama dosyasında görünmelidir. Dış ad, diğer uygulamalara sunulan OLE denetiminin tanımlayıcısıdır. Kapsayıcılar bu denetim sınıfının bir nesnesini istemek için bu adı kullanır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="begin_olefactory"></a><a name="begin_olefactory"></a> BEGIN_OLEFACTORY

Denetim sınıfınızın üstbilgi dosyasında sınıf fabrikanızın bildirimini başlatır.

```
BEGIN_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıf fabrikası bu olan denetim sınıfının adını belirtir.

### <a name="remarks"></a>Açıklamalar

Sınıf fabrikası lisanslama işlevlerinin bildirimleri BEGIN_OLEFACTORY hemen sonra başlamalıdır.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="end_olefactory"></a><a name="end_olefactory"></a> END_OLEFACTORY

Denetiminizin sınıf fabrikasının bildirimini sonlandırır.

```
END_OLEFACTORY(class_name)
```

### <a name="parameters"></a>Parametreler

*class_name*<br/>
Sınıf fabrikası olan denetim sınıfının adı.

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="afxverifylicfile"></a><a name="afxverifylicfile"></a> AfxVerifyLicFile

Tarafından adlandırılan lisans dosyasının `pszLicFileName` OLE denetimi için geçerli olduğunu doğrulamak için bu işlevi çağırın.

```
BOOL AFXAPI AfxVerifyLicFile(
    HINSTANCE  hInstance,
    LPCTSTR  pszLicFileName,
    LPOLESTR  pszLicFileContents,
    UINT cch = -1);
```

### <a name="parameters"></a>Parametreler

*HINSTANCE*<br/>
Lisanslı denetimle ilişkili DLL 'nin örnek tanıtıcısı.

*pszLicFileName*<br/>
Lisans dosya adını içeren null ile sonlandırılmış bir karakter dizesini işaret eder.

*pszLicFileContents*<br/>
Lisans dosyasının başlangıcında bulunan sırayla eşleşmesi gereken bir bayt dizisine işaret eder.

*CCH*<br/>
*PszLicFileContents* içindeki karakter sayısı.

### <a name="return-value"></a>Dönüş Değeri

Lisans dosyası varsa sıfır dışında ve *pszLicFileContents*; karakter dizisiyle başlıyorsa Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

*CCH* -1 ise, bu işlev şunları kullanır:

[!code-cpp[NVC_MFC_Utilities#36](../../mfc/codesnippet/cpp/class-factories-and-licensing_2.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** afxctl. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
