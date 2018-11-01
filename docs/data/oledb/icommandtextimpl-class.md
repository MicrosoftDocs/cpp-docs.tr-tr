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
ms.openlocfilehash: fafd1198776c558ff39ef35c0b7beca538e976ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677701"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl Sınıfı

Bir uygulamasını sağlar [ICommandText](/previous-versions/windows/desktop/ms714914) arabirimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T >
class ATL_NO_VTABLE ICommandTextImpl
   : public ICommandImpl<T, ICommandText>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Komut sınıfı türetilen `ICommandTextImpl`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** altdb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[GetCommandText](#getcommandtext)|Son çağrısı tarafından ayarlanan metin komutu döndürür [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).|
|[SetCommandText](#setcommandtext)|Mevcut komut metni değiştirme komut metni, ayarlar.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_strCommandText](#strcommandtext)|Komut metni depolar.|

## <a name="remarks"></a>Açıklamalar

Zorunlu bir arabirim açma komutları.

## <a name="getcommandtext"></a> Icommandtextımpl::getcommandtext

Son çağrısı tarafından ayarlanan metin komutu döndürür [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetCommandText)(GUID * pguidDialect, 
   LPOLESTR * ppwszCommand);
```

#### <a name="parameters"></a>Parametreler

Bkz: [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825) içinde *OLE DB Programcının Başvurusu*. *PguidDialect* parametre varsayılan olarak sayılır.

## <a name="setcommandtext"></a> Icommandtextımpl::setCommandText

Mevcut komut metni değiştirme komut metni, ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect, 
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>Parametreler

Bkz: [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757) içinde *OLE DB Programcının Başvurusu*.

## <a name="strcommandtext"></a> Icommandtextımpl::m_strCommandText

Komut metni dizesi depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)