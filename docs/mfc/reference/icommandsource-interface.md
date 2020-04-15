---
title: ICommandSource Arayüzü
ms.date: 03/27/2019
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
helpviewer_keywords:
- ICommandSource interface [MFC]
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
ms.openlocfilehash: 6a03c46c972f7746f39a3c5c65ca9b5509983d59
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81356988"
---
# <a name="icommandsource-interface"></a>ICommandSource Arayüzü

Komut kaynağı nesnesinden gönderilen komutları kullanıcı denetimine yönetir.

## <a name="syntax"></a>Sözdizimi

```cpp
interface class ICommandSource
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Komut kaynağı nesneye komut işleyicisi ekler.|
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Komut kaynağı nesneye bir komut işleyicileri grubu ekler.|
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Bir komut kaynağı nesneye bir grup kullanıcı arabirimi komut ileti iletisi işleyicileri grubu ekler.|
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Bir komut kaynağı nesneye kullanıcı arabirimi komut ileti sleyicisi ekler.|
|[ICommandSource::PostCommand](#postcommand)|İletinin işlenmesini beklemeden ileti gönderir.|
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Komut kaynağı nesnesinden bir komut işleyicisi kaldırır.|
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Komut kaynağı nesnesinden bir komut işleyicileri grubunu kaldırır.|
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Bir grup kullanıcı arabirimi komut ileti iletisini komut kaynağı nesneden kaldırır.|
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Bir komut kaynağı nesnesinden bir kullanıcı arabirimi komut ileti ileti işleyicisi kaldırır.|
|[ICommandSource::SendCommand](#sendcommand)|İleti gönderir ve dönmeden önce işlenmesini bekler.|

### <a name="remarks"></a>Açıklamalar

Bir MFC Görünümü'nde bir kullanıcı denetimi barındırdığınızda, [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md) komutları yönlendirir ve Komut UI iletilerini kullanıcı denetimine günceller ve MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemesine izin verir. [ICommandTarget Arabirimi](../../mfc/reference/icommandtarget-interface.md)uygulayarak, kullanıcı denetimi `ICommandSource` nesneye bir başvuru verir.

[Bkz. Nasıl Yapılır: Nasıl](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) kullanılacağına `ICommandTarget`bir örnek olarak Windows Forms Denetimi'ne Komut Yönlendirme ekleme.

Windows Formlarını kullanma hakkında daha fazla bilgi [için](../../dotnet/using-a-windows-form-user-control-in-mfc.md)bkz.

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (montaj atlmfc\lib\mfcmifc80.dll tanımlanır)

## <a name="icommandsourceaddcommandhandler"></a><a name="addcommandhandler"></a>ICommandSource::AddCommandHandler

Komut kaynağı nesneye komut işleyicisi ekler.

```cpp
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.
*cmdHandler*<br/>
Komut işleyicisi yöntemine bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem komut kaynağı nesnesine komut işleyicisi cmdHandler ekler ve işleyiciyi cmdID eşler.
Bkz. Nasıl Yapılır: AddCommandHandler'ın nasıl kullanılacağına bir örnek olarak [Windows Forms Control'e Komut Yönlendirme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) ekleme.

## <a name="icommandsourceaddcommandrangehandler"></a><a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler

Komut kaynağı nesneye bir komut işleyicileri grubu ekler.

```cpp
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut kimliği aralığının başlangıç dizini.
*cmdIDMax*<br/>
Komut kimliği aralığının bitiş dizini.
*cmdHandler*<br/>
Komutların eşlendiği ileti işleyicisi yönteminin tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bitişik bir komut dizisini tek bir ileti işleyicisine eşler ve komut kaynağı nesneye ekler. Bu, bir yöntemle ilgili düğmeler grubunu işlemek için kullanılır.

## <a name="icommandsourceaddcommandrangeuihandler"></a><a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler

Bir komut kaynağı nesneye bir grup kullanıcı arabirimi komut ileti iletisi işleyicileri grubu ekler.

```cpp
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut kimliği aralığının başlangıç dizini.
*cmdIDMax*<br/>
Komut kimliği aralığının bitiş dizini.
*cmdHandler*<br/>
Komutların eşlendiği ileti işleyicisi yönteminin tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bitişik bir komut birimi aralığını tek bir kullanıcı arabirimi komut ileti sikileyicisine eşler ve komut kaynağı nesneye ekler. Bu, bir yöntemle ilgili düğmeler grubunu işlemek için kullanılır.

## <a name="icommandsourceaddcommanduihandler"></a><a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler

Bir komut kaynağı nesneye kullanıcı arabirimi komut ileti sleyicisi ekler.

```cpp
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.
*cmdUIHandler*<br/>
Kullanıcı arabirimi komut ileti sileyici yöntemiiçin bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynağı nesnesine kullanıcı arabirimi komut ileti sileyici cmdHandler ekler ve işleyicisi cmdID eşler.

## <a name="icommandsourcepostcommand"></a><a name="postcommand"></a>ICommandSource::PostCommand

İletinin işlenmesini beklemeden ileti gönderir.

```cpp
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*Komut*<br/>
Deftere nakledilecek iletinin komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut tarafından belirtilen kimlik eşlenen ileti eşlemeli olarak gönderir. CWnd::PostMessage'ı pencerenin ileti sırasına yerleştirmek için çağırır ve ardından ilgili pencerenin iletiyi işlemesini beklemeden döndürür.

## <a name="icommandsourceremovecommandhandler"></a><a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler

Komut kaynağı nesnesinden bir komut işleyicisi kaldırır.

```cpp
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, cmdID eşlenen komut işleyicisini komut kaynağı nesnesinden kaldırır.

## <a name="icommandsourceremovecommandrangehandler"></a><a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler

Komut kaynağı nesnesinden bir komut işleyicileri grubunu kaldırır.

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut kimliği aralığının başlangıç dizini.
*cmdIDMax*<br/>
Komut kimliği aralığının bitiş dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, cmdIDMin ve cmdIDMax tarafından belirtilen komut kimliklerine eşlenen bir grup ileti işleyicisini komut kaynağı nesnesinden kaldırır.

## <a name="icommandsourceremovecommandrangeuihandler"></a><a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler

Bir grup kullanıcı arabirimi komut ileti iletisini komut kaynağı nesneden kaldırır.

```cpp
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut kimliği aralığının başlangıç dizini.
*cmdIDMax*<br/>
Komut kimliği aralığının bitiş dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, cmdIDMin ve cmdIDMax tarafından belirtilen komut kimliklerine eşlenen bir grup kullanıcı arabirimi komut ileti ileti işleyicisini komut kaynağı nesnesinden kaldırır.

## <a name="icommandsourceremovecommanduihandler"></a><a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler

Bir komut kaynağı nesnesinden bir kullanıcı arabirimi komut ileti ileti işleyicisi kaldırır.

```cpp
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, cmdID'ye eşlenen kullanıcı arabirimi komut ileti selini komut kaynağı nesnesinden kaldırır.

## <a name="icommandsourcesendcommand"></a><a name="sendcommand"></a>ICommandSource::SendCommand

İleti gönderir ve dönmeden önce işlenmesini bekler.

```cpp
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*Komut*<br/>
Gönderilecek iletinin komut kimliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut tarafından belirtilen kimlik eşlenen ileti yi eşlemeli olarak gönderir. CWnd çağırır::İletiyi pencerenin ileti kuyruğuna yerleştirmek için İleti Gönder ve bu pencere yordamı döndürülmeden önce iletiyi işleyene kadar bekler.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandTarget Arayüzü](../../mfc/reference/icommandtarget-interface.md)
