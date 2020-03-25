---
title: ICommandTextImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ICommandText
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
- ATL::ICommandTextImpl::m_strCommandText
- ICommandTextImpl<T>::m_strCommandText
- m_strCommandText
- ICommandTextImpl.m_strCommandText
- ICommandTextImpl::m_strCommandText
- ATL::ICommandTextImpl<T>::m_strCommandText
- ATL.ICommandTextImpl.m_strCommandText
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
helpviewer_keywords:
- ICommandText class
- GetCommandText method
- m_strCommandText
- SetCommandText method
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
ms.openlocfilehash: d91221dd509122ebbd6490c2de7fab1ce51eb2f8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210736"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl Sınıfı

[ICommandText](/previous-versions/windows/desktop/ms714914(v=vs.85)) arabirimi için bir uygulama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T >
class ATL_NO_VTABLE ICommandTextImpl
   : public ICommandImpl<T, ICommandText>
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
`ICommandTextImpl`türetilen komut sınıfı.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** altdb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetCommandText](#getcommandtext)|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)' e yapılan son çağrı tarafından ayarlanan metin komutunu döndürür.|
|[SetCommandText](#setcommandtext)|Komut metnini ayarlar ve varolan komut metnini değiştirir.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_strCommandText](#strcommandtext)|Komut metnini depolar.|

## <a name="remarks"></a>Açıklamalar

Komutlarda zorunlu arabirim.

## <a name="icommandtextimplgetcommandtext"></a><a name="getcommandtext"></a>ICommandTextImpl:: GetCommandText

[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)' e yapılan son çağrı tarafından ayarlanan metin komutunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetCommandText)(GUID * pguidDialect,
   LPOLESTR * ppwszCommand);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ICommandText:: GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) ' i inceleyin. *PguidDialect* parametresi varsayılan olarak yok sayılır.

## <a name="icommandtextimplsetcommandtext"></a><a name="setcommandtext"></a>ICommandTextImpl:: SetCommandText

Komut metnini ayarlar ve varolan komut metnini değiştirir.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ICommandText:: setCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) ' i inceleyin.

## <a name="icommandtextimplm_strcommandtext"></a><a name="strcommandtext"></a>ICommandTextImpl:: m_strCommandText

Komut metni dizesini depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
