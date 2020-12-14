---
description: 'Daha fazla bilgi edinin: TN039: MFC/OLE Otomasyon uygulama'
title: 'TN039: MFC-OLE Otomasyon uygulama'
ms.date: 06/28/2018
helpviewer_keywords:
- MFC, COM support
- IDispatch interface
- MFC, OLE DB and
- TN039
- Automation, MFC COM interface entry points
ms.assetid: 765fa3e9-dd54-4f08-9ad2-26e0546ff8b6
ms.openlocfilehash: caabd3719a467e534e47ca61ed8f9a9f1f0d2eb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215423"
---
# <a name="tn039-mfcole-automation-implementation"></a>TN039: MFC/OLE Otomasyon Uygulaması

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

## <a name="overview-of-ole-idispatch-interface"></a>OLE IDispatch arabirimine genel bakış

`IDispatch`Arabirim, uygulamalar Için VISUAL BASIC veya diğer diller gibi diğer uygulamaların uygulama özelliklerinden yararlanarak Yöntemler ve Özellikler sergileme yöntemidir. Bu arabirimin en önemli bölümü, `IDispatch::Invoke` işlevidir. MFC, uygulamak için "dağıtım haritaları" kullanır `IDispatch::Invoke` . Dağıtım eşlemesi, MFC Uygulama bilgilerini, türetilmiş sınıflarınızın düzen veya "Shape" `CCmdTarget` ' i içinde sağlar. bu şekilde nesnenin özelliklerini doğrudan işleyebilir ya da istekleri karşılamak için nesnenizin içindeki üye işlevlerini çağırabilirsiniz `IDispatch::Invoke` .

Çoğu bölüm olan ClassWizard ve MFC birlikte çalışması için, Uygulama programcılarından OLE otomasyonunun ayrıntılarının çoğunu gizleyin. Programcı, uygulamada kullanıma sunulacak gerçek işlevselliğe yoğunlaşır ve temel alınan sıhhi tesisat hakkında endişelenmenize gerek kalmaz.

Ancak, ne tür bir MFC 'nin arka planda çalıştığını anlamak için gereken durumlar vardır. Bu notta, Framework 'ün, üye işlevlerine ve özelliklerine nasıl **SPID**'leri atayacağı ele alınacaktır. MFC 'nin bir "tür kitaplığı" oluşturma , örneğin, uygulama nesneleri için bir "tür kitaplığı" oluştururken yalnızca kimlikleri bilmeniz gerektiğinde gereklidir.

## <a name="mfc-dispid-assignment"></a>MFC DISPID ataması

Otomasyon 'un son kullanıcısı (örneğin, bir Visual Basic Kullanıcı), Otomasyon etkin özelliklerinin ve yöntemlerinin (obj gibi) gerçek adlarını görür. ShowWindow), uygulamasının uygulanması `IDispatch::Invoke` gerçek adları almaz. En iyi duruma getirme nedenleriyle, erişilecek yöntemi veya özelliği açıklayan 32 bitlik bir "sihirli tanımlama bilgisi" olan bir **DISPID** alır. Bu **DISPID** değerleri `IDispatch` , uygulamasından, adlı başka bir yöntem aracılığıyla döndürülür `IDispatch::GetIDsOfNames` . Otomasyon istemci uygulaması `GetIDsOfNames` , erişmeyi amaçladığı her üye veya özellik için bir kez çağrı yapılır ve daha sonra çağrıları için önbelleğe alınır `IDispatch::Invoke` . Bu şekilde, pahalı dize arama, her çağrı için bir kez değil, nesne kullanımı başına yalnızca bir kez gerçekleştirilir `IDispatch::Invoke` .

MFC her bir yöntem ve özellik için her iki şeyi temel alarak bir **SPID**'leri belirler:

- Dağıtım eşlemesinin en üstünden uzaklık (1 göreli)

- Dağıtım haritasının en çok türetilen sınıftan uzaklığı (0 göreli)

**DISPID** iki parçaya bölünür. **DISPID** 'Nin **LOWORD** 'i, dağıtım eşlemesinin en üstünden uzaklık olan ilk bileşeni içerir. **Hiword** , en çok türetilen sınıftan uzaklığı içerir. Örneğin:

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

Gördüğünüz gibi, her ikisi de OLE Otomasyon arabirimlerini sunan iki sınıf vardır. Bu sınıflardan biri diğerine türetilir ve bu nedenle, OLE Otomasyon Bölümü (Bu durumda "x" ve "y" özellikleri) dahil olmak üzere temel sınıfın işlevselliğinden yararlanır.

MFC, sınıf CDispPoint için aşağıdaki gibi bir **DISPID** üretir:

```cpp
property X    (DISPID)0x00000001
property Y    (DISPID)0x00000002
```

Özellikler bir temel sınıfta olmadığından, **DISPID** 'nin **hibkelimesi** her zaman sıfırdır (CDispPoint için en fazla türetilen sınıftan uzaklık sıfırdır).

MFC, CDisp3DPoint sınıfı için aşağıdaki şekilde bir **DISPID** üretir:

```cpp
property Z    (DISPID)0x00000001
property X    (DISPID)0x00010001
property Y    (DISPID)0x00010002
```

Z özelliğine, CDisp3DPoint özelliklerini kullanıma sunan sınıfta tanımlandığından, sıfır **hiıt** Ile bir **DISPID** verilir. X ve Y özellikleri bir temel sınıfta tanımlandığından, bu özelliklerin tanımlandığı sınıf, en türetilmiş sınıftan bir Türetmenin mesafesinde olduğundan, **DISPID** 'nin **hibisi** 1 ' dir.

> [!NOTE]
> **LOWORD** , haritada açık bir **DISPID** ile var olan girişler olsa bile her zaman eşlemedeki konuma göre belirlenir (ve makroların **_ID** sürümleri hakkında daha fazla bilgi için sonraki bölüme bakın `DISP_PROPERTY` `DISP_FUNCTION` ).

## <a name="advanced-mfc-dispatch-map-features"></a>Gelişmiş MFC dağıtım eşleme özellikleri

ClassWizard 'ın bu Visual C++ sürümünde desteklemediği bazı ek özellikler vardır. ClassWizard, `DISP_FUNCTION` `DISP_PROPERTY` `DISP_PROPERTY_EX` sırasıyla bir yöntemi, üye değişkeni özelliğini ve Get/Set üye işlevi özelliğini destekler, ve tanımlar. Bu yetenekler genellikle çoğu Otomasyon sunucusunu oluşturmak için gereklidir.

Aşağıdaki ek makrolar, ClassWizard 'ın desteklediği makrolar yeterli olmadığında kullanılabilir: `DISP_PROPERTY_NOTIFY` , ve `DISP_PROPERTY_PARAM` .

## <a name="disp_property_notify--macro-description"></a>DISP_PROPERTY_NOTIFY — makro açıklaması

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    pszName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Parametreler

*Sınıf*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*memberName*<br/>
Özelliğin depolandığı üye değişkeninin adı.

*pfnAfterSet*<br/>
Özellik değiştirildiğinde çağrılacak üye işlevin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

### <a name="remarks"></a>Açıklamalar

Bu makro, DISP_PROPERTY ek bir bağımsız değişken kabul ettiğinden çok benzer. Ek bağımsız değişken olan *pfnAfterSet,* hiçbir şey döndüren ve hiçbir parametre alan (' void OnPropertyNotify () ') bir üye işlev olmalıdır. Üye değişkeni değiştirildikten **sonra** çağrılacaktır.

## <a name="disp_property_param--macro-description"></a>DISP_PROPERTY_PARAM — makro açıklaması

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

*Sınıf*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*memberGet*<br/>
Özelliği almak için kullanılan üye işlevinin adı.

*memberSet*<br/>
Özelliği ayarlamak için kullanılan üye işlevinin adı.

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

*vtsParams*<br/>
Her parametre için boşlukla ayrılmış bir dize VTS_.

### <a name="remarks"></a>Açıklamalar

DISP_PROPERTY_EX makrosuna benzer şekilde, bu makro ayrı Get ve set member işlevleriyle erişilen bir özelliği tanımlar. Ancak, bu makro, özelliği için bir parametre listesi belirtmenize izin verir. Bu, başka bir şekilde dizini oluşturulmuş veya parametreli olan özellikleri uygulamak için yararlıdır. Parametreler her zaman ilk olarak yerleştirilir ve sonra özelliğin yeni değeri gelir. Örneğin:

```cpp
DISP_PROPERTY_PARAM(CMyObject, "item", GetItem, SetItem, VT_DISPATCH, VTS_I2 VTS_I2)
```

üye işlevlerini al ve ayarla öğesine karşılık gelir:

```cpp
LPDISPATCH CMyObject::GetItem(short row, short col)
void CMyObject::SetItem(short row, short col, LPDISPATCH newValue)
```

## <a name="disp_xxxx_id--macro-descriptions"></a>DISP_XXXX_ID — makro açıklamaları

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

*Sınıf*<br/>
Sınıfın adı.

*pszName*<br/>
Özelliğin dış adı.

*dı*<br/>
Özellik veya yöntem için sabit DISPID.

*pfnGet*<br/>
Özelliği almak için kullanılan üye işlevinin adı.

*pfnSet*<br/>
Özelliği ayarlamak için kullanılan üye işlevinin adı.

*memberName*<br/>
Özelliğe eşlenecek üye değişkeninin adı

*vtPropType*<br/>
Özelliğin türünü belirten bir değer.

*vtsParams*<br/>
Her parametre için boşlukla ayrılmış bir dize VTS_.

### <a name="remarks"></a>Açıklamalar

Bu makrolar, MFC 'nin otomatik olarak bir tane atamasını sağlamak yerine bir **DISPID** belirtmenize olanak tanır. Bu gelişmiş makrolar, KIMLIğIN makro adına eklendiği (örn. **DISP_PROPERTY_ID**) ve kimlik, yalnızca *pszName* parametresinden hemen sonra belirtilen parametreye göre belirlenir. Bkz. AFXDISP. Bu makrolar hakkında daha fazla bilgi için. **_ID** girdileri, dağıtım haritasının sonuna yerleştirilmelidir. Otomatik **SPID** oluşturmayı, makronun **_ID** olmayan bir sürümüyle aynı şekilde etkiler ( **DISPID**'lar konuma göre belirlenir). Örneğin:

```cpp
BEGIN_DISPATCH_MAP(CDisp3DPoint, CCmdTarget)
    DISP_PROPERTY(CDisp3DPoint, "y", m_y, VT_I2)
    DISP_PROPERTY(CDisp3DPoint, "z", m_z, VT_I2)
    DISP_PROPERTY_ID(CDisp3DPoint, "x", 0x00020003, m_x, VT_I2)
END_DISPATCH_MAP()
```

MFC, CDisp3DPoint sınıfı için aşağıdaki şekilde bir DISPID üretir:

```cpp
property X    (DISPID)0x00020003
property Y    (DISPID)0x00000002
property Z    (DISPID)0x00000001
```

Sabit bir **DISPID** belirtmek, daha önce varolan bir dağıtım arabirimine geriye dönük uyumluluk sağlamak ya da belirli sistem tanımlı yöntemleri veya özellikleri (genellikle **DISPID_NEWENUM** koleksiyonu gibi bir negatif **DISPID** tarafından belirtilir) uygulamak için yararlıdır.

## <a name="retrieving-the-idispatch-interface-for-a-coleclientitem"></a>Colet Clientıtem için IDispatch arabirimini alma

Birçok sunucu, OLE sunucu işlevselliğiyle birlikte belge nesnelerinde Otomasyonu destekleyecektir. Bu Otomasyon arabirimine erişim kazanmak için üye değişkenine doğrudan erişmek gerekir `COleClientItem::m_lpObject` . Aşağıdaki kod, `IDispatch` öğesinden türetilmiş bir nesnenin arabirimini alır `COleClientItem` . Gerekli olan bu işlevselliği bulursanız, aşağıdaki kodu uygulamanıza ekleyebilirsiniz:

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

Bu işlevden döndürülen dağıtım arabirimi daha sonra doğrudan veya `COleDispatchDriver` tür kullanımı uyumlu erişim için bir öğesine iliştirilebilir. Doğrudan kullanıyorsanız, `Release` işaretçisini işaretçiyle ( `COleDispatchDriver` yok edici bunu varsayılan olarak yapar) çağırdığınızdan emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
