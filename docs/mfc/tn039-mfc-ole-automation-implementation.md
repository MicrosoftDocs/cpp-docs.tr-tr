---
title: 'TN039: MFC-OLE Otomasyon uygulaması'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.ole
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
ms.openlocfilehash: cd6f8d681ef7e6517f2172ca6b22b13723a962fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305495"
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039: MFC/OLE Otomasyon uygulaması

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

## <a name="overview-of-ole-idispatch-interface"></a>OLE IDispatch arabirimi genel bakış

`IDispatch` Arabirimidir uygulamaları tarafından açığa diğer uygulamalar gibi Visual BASIC veya diğer dillerde yapabileceğiniz gibi uygulamanın özelliklerini kullandığınız yöntemleri ve özellikleri anlamına gelir. Bu arabirim, en önemli parçasıdır `IDispatch::Invoke` işlevi. MFC kullanan "gönderme eşlemeleri" uygulamak için `IDispatch::Invoke`. Dağıtım eşlemesi düzenini veya "şeklini" MFC Uygulama bilgileri sağlar, `CCmdTarget`-doğrudan nesnenin özelliklerini değiştirmek veya üye işlevlerini karşılamak için nesne içinde sınıflar türetilmiş `IDispatch::Invoke` istek sayısı.

Çoğunlukla, ClassWizard ve MFC OLE Otomasyon Uygulaması Programcı ayrıntılarını çoğunu gizlemek üzere işbirliği yapar. Programcı uygulamada göstermek için gerçek işlevlerini yoğunlaşır ve temel alınan tesisat hakkında endişelenmenize gerek yoktur.

MFC arka planda ne yaptığını anlamak için gerekli olduğu durumlar vardır. Bu Not nasıl framework atar adres **DISPID**s üye işlevleri ve özellikleri. MFC kullanan atamak için algoritma bilgi **DISPID**s olduğunda yalnızca gerekli uygulama nesneleri için bir "tür kitaplığı" oluşturduğunuzda gibi kimlikleri, bilmeniz gerekir.

## <a name="mfc-dispid-assignment"></a>MFC DISPID atama

Otomasyon (Visual Basic kullanıcı, örneğin), son kullanıcı görür ancak gerçek adlarını Otomasyon özellikleri ve yöntemleri (örneğin, obj. kendi kodundaki etkin ShowWindow) uygulamasını `IDispatch::Invoke` gerçek adlarını almaz. En iyi duruma getirme nedenlerle aldığı bir **DISPID**, "yöntem veya erişilecek özellik açıklayan bir 32-bit Sihirli tanımlama bilgisi" olduğu. Bunlar **DISPID** sağlayıcıdan döndürülen değerleri `IDispatch` adlı başka bir yöntem aracılığıyla uygulama `IDispatch::GetIDsOfNames`. Bir otomasyon istemci uygulamasını çağıracak `GetIDsOfNames` her üyesi veya özelliği için erişmek ve bunları sonraki çağrılar için önbellek amaçlamaktadır sonra `IDispatch::Invoke`. Bu şekilde, pahalı dize arama yalnızca bir kez nesne kullanımı yerine bir kez başına yapılır `IDispatch::Invoke` çağırın.

MFC belirler **DISPID**s için her bir yöntem ve özellik tabanlı iki şey üzerinde:

- Dağıtım eşlemesi (1 göreli) üst mesafe

- Dağıtım eşlemesi (göreli 0) en çok türetilen sınıftaki uzaklığı

**DISPID** iki bölüme ayrılır. **GET_X_LPARAM** , **DISPID** ilk bileşen, dağıtım eşlemesi üstünden uzaklık içerir. **Get_y_lparam kullanın** en çok türetilen sınıf olan uzaklık içerir. Örneğin:

```cpp
class CDispPoint : public CCmdTarget
{
public:
    short m_x, m_y;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

class CDisp3DPoint : public CDispPoint
{
public:
    short m_z;
    // ...
    DECLARE_DISPATCH_MAP()
    // ...
};

BEGIN_DISPATCH_MAP(CDispPoint, CCmdTarget)
    DISP_PROPERTY(CDispPoint, "x", m_x, VT_I2)
    DISP_PROPERTY(CDispPoint, "y", m_y, VT_I2)
END_DISPATCH_MAP()

BEGIN_DISPATCH_MAP(CDisp3DPoint, CDispPoint)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
END_DISPATCH_MAP()
```

Gördüğünüz gibi ikisi için de OLE Otomasyon arabirimleri kullanıma sunar, iki sınıf vardır. Bu sınıflardan biri diğerinden türetilir ve bu nedenle temel sınıfın işlevselliği, OLE Otomasyon dahil yararlanır ("x" ve "y" özellikleri bu durumda).

MFC oluşturacağını **DISPID**s CDispPoint gibi sınıf:

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

Özellikleri bir temel sınıfta olmadığından **get_y_lparam kullanın** , **DISPID** her zaman sıfır (en çok türetilen sınıf için CDispPoint mesafe sıfırsa) olur.

MFC oluşturacağını **DISPID**s CDisp3DPoint gibi sınıf:

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

Z özelliğini verilen bir **DISPID** sıfır **get_y_lparam kullanın** CDisp3DPoint özelliklerini gösterme sınıfında tanımlamış. X ve Y özellikleri bir temel sınıfta tanımlanan beri **get_y_lparam kullanın** , **DISPID** bu özellikleri tanımlandığı sınıfın en çok türetilen sınıftaki bir türetme uzaklıkta olduğundan 1 ' dir.

> [!NOTE]
> **GET_X_LPARAM** açık ile eşleme girişleri bulunsa bile her zaman harita konumu tarafından belirlenir **DISPID** (bilgi için sonraki bölüme bakın **_kimliği** sürümleri `DISP_PROPERTY` ve `DISP_FUNCTION` makroları).

## <a name="advanced-mfc-dispatch-map-features"></a>Gelişmiş MFC gönderme eşleme özellikleri

Visual C++'ın bu sürümüyle ClassWizard desteği olmayan ek özellikler birkaç vardır. ClassWizard destekler `DISP_FUNCTION`, `DISP_PROPERTY`, ve `DISP_PROPERTY_EX` , tanımladığınız bir yöntemi, üye değişkeni özelliğinin ve üye işlev özellik alma/ayarlama, sırasıyla. Bu özellikler genellikle çoğu otomasyon sunucuları oluşturmak için gerekli değildir.

Aşağıdaki ek makroları ClassWizard desteklenen makrolar yeterli olmadığında kullanılabilir: `DISP_PROPERTY_NOTIFY`, ve `DISP_PROPERTY_PARAM`.

## <a name="disppropertynotify--macro-description"></a>Dısp_property_notıfy — Makro tanımı

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*memberName*<br/>
Özellik depolandığı üye değişkeninin adı.

*pfnAfterSet*<br/>
Özellik değiştiğinde çağrılacak üye işlevinin adı.

*vtPropType*<br/>
Özelliğin türü belirten bir değeri.

### <a name="remarks"></a>Açıklamalar

Bu makro çok dısp_property gibi ek bağımsız değişken kabul dışında aynıdır. Ek bağımsız değişken *pfnAfterSet,* nothing döndürür ve hiçbir parametre 'void OnPropertyNotify()' geçen bir üye işlevi olmalıdır. Çağrılacağı **sonra** üye değişkeni değiştirildi.

## <a name="disppropertyparam--macro-description"></a>Dısp_property_param — Makro tanımı

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*memberGet*<br/>
Özelliği almak için kullanılan bir üye işlevin adı.

*memberSet*<br/>
Özelliği ayarlamak için kullanılan bir üye işlevin adı.

*vtPropType*<br/>
Özelliğin türü belirten bir değeri.

*vtsParams*<br/>
Bir dize alanı VTS_ her parametre için ayrılmış.

### <a name="remarks"></a>Açıklamalar

Çok dısp_property_ex makrosu gibi ayrı Get ve Set üye işlevleri ile erişilen bir özelliği bu makroyu tanımlar. Bu makro ancak özelliğinin bir parametre listesini belirtmenize olanak tanır. Bu, başka bir şekilde dizine veya parametreli özellikleri uygulamak için kullanışlıdır. Parametreleri her zaman ilk olarak, özelliğinin yeni değeri ardında yer alır. Örneğin:

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

GET ve set üye işlevleri karşılık gelir:

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="dispxxxxid--macro-descriptions"></a>DISP_XXXX_ID — Makro tanımları

```cpp
DISP_FUNCTION_ID(
    theClass,
    pszName,
    dispid,
    pfnMember,
    vtRetVal,
    vtsParams)
DISP_PROPERTY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    vtPropType)
DISP_PROPERTY_NOTIFY_ID(
    theClass,
    pszName,
    dispid,
    memberName,
    pfnAfterSet,
    vtPropType)
DISP_PROPERTY_EX_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType)
DISP_PROPERTY_PARAM_ID(
    theClass,
    pszName,
    dispid,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Parametreler

*Sınıfın*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*DISPID*<br/>
Özellik veya yöntem için sabit DISPID.

*pfnGet*<br/>
Özelliği almak için kullanılan bir üye işlevin adı.

*pfnSet*<br/>
Özelliği ayarlamak için kullanılan bir üye işlevin adı.

*memberName*<br/>
Özelliğini eşleştirmek için üye değişkeninin adı

*vtPropType*<br/>
Özelliğin türü belirten bir değeri.

*vtsParams*<br/>
Bir dize alanı VTS_ her parametre için ayrılmış.

### <a name="remarks"></a>Açıklamalar

Bu makrolar belirtmenizi sağlar bir **DISPID** MFC otomatik olarak izin vermek yerine atayın. Bu kimliği için makro adı eklenir dışında bu makrolar Gelişmiş aynı ada sahip (örneğin **DISP_PROPERTY_ID**) ve sonra yalnızca belirtilen parametre tarafından kimliği belirlenir *pszName* parametresi. AFXDISP bakın. Bu makrolar hakkında daha fazla bilgi için H. **_Kimliği** girişleri dağıtım eşlemesi sonunda yerleştirilmelidir. Bunlar otomatik etkiler **DISPID** aynı olmayan bir şekilde oluşturma **_kimliği** makro sürümü gerekir ( **DISPID**s konumu tarafından belirlenir). Örneğin:

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC DISPID değeri, şu şekilde CDisp3DPoint sınıfı için'ı oluşturun:

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

Bir sabit belirtmek **DISPID** önceden var olan bir dağıtım arabirimi için geriye dönük uyumluluk sağlamak ya da belirli bir sistem tanımlı yöntem ya da özellikleri uygulamak için kullanışlıdır (genellikle bir negatif tarafından belirtilen  **DISPID**, gibi **DISPID_NEWENUM** koleksiyonu).

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>Bir Coleclientıtem IDispatch arabirimi alınıyor

Birçok sunucuya OLE sunucu işlevselliğinin yanı sıra kendi belge nesneleri içinde Otomasyonu destekler. Bu Otomasyon arabirim erişim kazanmak için doğrudan erişim için gerekli olan `COleClientItem::m_lpObject` üye değişkeni. Aşağıdaki kodu alacak `IDispatch` türetilen bir nesne için arabirim `COleClientItem`. Bu işlev gerekli bulursanız, uygulamanızda aşağıdaki kod şunları içerebilir:

```cpp
LPDISPATCH CMyClientItem::GetIDispatch()
{
    ASSERT_VALID(this);
    ASSERT(m_lpObject != NULL);

    LPUNKNOWN lpUnk = m_lpObject;

    Run();      // must be running

    LPOLELINK lpOleLink = NULL;
    if (m_lpObject->QueryInterface(IID_IOleLink,
        (LPVOID FAR*)&lpOleLink) == NOERROR)
    {
        ASSERT(lpOleLink != NULL);
        lpUnk = NULL;
        if (lpOleLink->GetBoundSource(&lpUnk) != NOERROR)
        {
            TRACE0("Warning: Link is not connected!\n");
            lpOleLink->Release();
            return NULL;
        }
        ASSERT(lpUnk != NULL);
    }

    LPDISPATCH lpDispatch = NULL;
    if (lpUnk->QueryInterface(IID_IDispatch, &lpDispatch) != NOERROR)
    {
        TRACE0("Warning: does not support IDispatch!\n");
        return NULL;
    }

    ASSERT(lpDispatch != NULL);
    return lpDispatch;
}
```

Dağıtım arabirimi döndürüldüğü bu işlev sonra doğrudan kullanılabilir veya iliştirilmiş bir `COleDispatchDriver` tür kullanımı uyumlu erişim için. Doğrudan kullanmanız durumunda çağırmanızı emin olun, `Release` üye işaretçisi olduğunda aracılığıyla ( `COleDispatchDriver` yok Edicisi bunu varsayılan olarak yapar).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
