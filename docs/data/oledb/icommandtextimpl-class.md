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
ms.openlocfilehash: de9e930056db7b91968ca1ce471a87809693376a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408985"
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl Sınıfı

Bir uygulamasını sağlar [ICommandText](/previous-versions/windows/desktop/ms714914(v=vs.85)) arabirimi.

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

Bkz: [ICommandText::GetCommandText](/previous-versions/windows/desktop/ms709825(v=vs.85)) içinde *OLE DB Programcının Başvurusu*. *PguidDialect* parametre varsayılan olarak sayılır.

## <a name="setcommandtext"></a> Icommandtextımpl::setCommandText

Mevcut komut metni değiştirme komut metni, ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(SetCommandText)(REFGUID rguidDialect,
   LPCOLESTR pwszCommand);
```

#### <a name="parameters"></a>Parametreler

Bkz: [ICommandText::SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="strcommandtext"></a> Icommandtextımpl::m_strCommandText

Komut metni dizesi depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
CComBSTR m_strCommandText;
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)