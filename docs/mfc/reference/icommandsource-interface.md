---
title: ICommandSource arabirimi
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
ms.openlocfilehash: a57ca6f36546a17b9a35ebea875ff01b43de1332
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445703"
---
# <a name="icommandsource-interface"></a>ICommandSource arabirimi

Bir komut kaynak nesnesinden kullanıcı denetimine gönderilen komutları yönetir.

## <a name="syntax"></a>Sözdizimi

```
interface class ICommandSource
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ICommandSource:: AddCommandHandler](#addcommandhandler)|Komut kaynak nesnesine bir komut işleyicisi ekler.|
|[ICommandSource:: AddCommandRangeHandler](#addcommandrangehandler)|Komut kaynak nesnesine bir komut işleyicileri grubu ekler.|
|[ICommandSource:: Addcommandrangeuıhandler](#addcommandrangeuihandler)|Komut kaynak nesnesine bir kullanıcı arabirimi komut ileti işleyicileri grubu ekler.|
|[ICommandSource:: AddCommandUIHandler](#addcommandrangeuihandler)|Komut kaynak nesnesine bir kullanıcı arabirimi komut iletisi işleyicisi ekler.|
|[ICommandText::P Ostsource:](#postcommand)|İşlenmek üzere beklemeden bir ileti gönderir.|
|[ICommandSource:: RemoveCommandHandler](#removecommandhandler)|Komut işleyicisini bir komut kaynak nesnesinden kaldırır.|
|[ICommandSource:: RemoveCommandRangeHandler](#removecommandrangehandler)|Bir komut işleyici grubunu bir komut kaynak nesnesinden kaldırır.|
|[ICommandSource:: Removecommandrangeuıhandler](#removecommandrangeuihandler)|Bir komut kaynak nesnesinden bir kullanıcı arabirimi komut ileti işleyicileri grubunu kaldırır.|
|[ICommandSource:: RemoveCommandUIHandler](#removecommandrangeuihandler)|Bir komut kaynak nesnesinden bir kullanıcı arabirimi komut iletisi işleyicisini kaldırır.|
|[ICommandSource:: SendCommand](#sendcommand)|Bir ileti gönderir ve döndürmeden önce işlenmesini bekler.|

### <a name="remarks"></a>Açıklamalar

Bir MFC görünümünde bir Kullanıcı Denetimi barındırdığınızda, [CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md) komutları YÖNLENDIRIR ve MFC komutlarını (örneğin, çerçeve menü öğeleri ve araç çubuğu düğmeleri) işlemesini sağlamak IÇIN komut UI iletilerini Kullanıcı denetimine güncelleştirir. [ICommandTarget arabirimini](../../mfc/reference/icommandtarget-interface.md)uygulayarak, kullanıcı denetimine `ICommandSource` nesnesine bir başvuru verirsiniz.

`ICommandTarget`nasıl kullanılacağına ilişkin bir örnek için bkz. [nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) .

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC 'de Windows formu Kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:** afxwinforms. h (Assembly atlmfc\lib\mfcmifc80.dll derlemesinde tanımlanmıştır)

## <a name="addcommandhandler"></a>ICommandSource:: AddCommandHandler

Komut kaynak nesnesine bir komut işleyicisi ekler.

```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.
*cmdHandler*<br/>
Komut işleyici yöntemine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem komut işleyicisi cmdHandler komutunu komut kaynak nesnesine ekler ve işleyiciyi cmdID 'e eşler.
AddCommandHandler 'nin nasıl kullanılacağına ilişkin bir örnek için, bkz. [nasıl yapılır: Windows Forms denetimine komut yönlendirmesi ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) .

## <a name="addcommandrangehandler"></a>ICommandSource:: AddCommandRangeHandler

Komut kaynak nesnesine bir komut işleyicileri grubu ekler.

```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut KIMLIĞI aralığının başlangıç dizini.
*cmdIDMax*<br/>
Komut KIMLIĞI aralığının bitiş dizini.
*cmdHandler*<br/>
Komutların eşlendiği ileti işleyicisi yöntemine yönelik bir tanıtıcı.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, bitişik bir komut kimliği aralığını tek bir ileti işleyicisine eşleştirir ve komut kaynak nesnesine ekler. Bu, bir ilişkili düğme grubunu tek bir yöntemle işlemek için kullanılır.

## <a name="addcommandrangeuihandler"></a>ICommandSource:: Addcommandrangeuıhandler

Komut kaynak nesnesine bir kullanıcı arabirimi komut ileti işleyicileri grubu ekler.

```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut KIMLIĞI aralığının başlangıç dizini.
*cmdIDMax*<br/>
Komut KIMLIĞI aralığının bitiş dizini.
*cmdHandler*<br/>
Komutların eşlendiği ileti işleyicisi yöntemine yönelik bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bitişik bir komut kimliği aralığını tek bir kullanıcı arabirimi komut iletisi işleyicisine eşleştirir ve komut kaynak nesnesine ekler. Bu, bir ilişkili düğme grubunu tek bir yöntemle işlemek için kullanılır.

## <a name="addcommanduihandler"></a>ICommandSource:: AddCommandUIHandler

Komut kaynak nesnesine bir kullanıcı arabirimi komut iletisi işleyicisi ekler.

```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.
*cmdUIHandler*<br/>
Kullanıcı arabirimi komut iletisi işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesnesine kullanıcı arabirimi komut iletisi işleyicisi cmdHandler ' i ekler ve işleyiciyi cmdID 'e eşler.

## <a name="postcommand"></a>ICommandText::P Ostsource:

İşlenmek üzere beklemeden bir ileti gönderir.

```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*komutundaki*<br/>
Nakledilecek iletinin komut KIMLIĞI.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut tarafından belirtilen KIMLIĞE eşlenen iletiyi zaman uyumsuz olarak gönderir. İletiyi pencerenin ileti kuyruğuna yerleştirmek için CWnd::P ostMessage çağırır ve sonra karşılık gelen pencerenin iletiyi işlemesini beklemeden geri döndürür.

## <a name="removecommandhandler"></a>ICommandSource:: RemoveCommandHandler

Komut işleyicisini bir komut kaynak nesnesinden kaldırır.

```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, cmdID ile eşlenen komut işleyicisini komut kaynak nesnesinden kaldırır.

## <a name="removecommandrangehandler"></a>ICommandSource:: RemoveCommandRangeHandler

Bir komut işleyici grubunu bir komut kaynak nesnesinden kaldırır.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut KIMLIĞI aralığının başlangıç dizini.
*cmdIDMax*<br/>
Komut KIMLIĞI aralığının bitiş dizini.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesnesinden cmdIDMin ve cmdIDMax tarafından belirtilen komut kimlikleriyle eşlenmiş bir ileti işleyicileri grubunu kaldırır.

## <a name="removecommandrangeuihandler"></a>ICommandSource:: Removecommandrangeuıhandler

Bir komut kaynak nesnesinden bir kullanıcı arabirimi komut ileti işleyicileri grubunu kaldırır.

```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut KIMLIĞI aralığının başlangıç dizini.
*cmdIDMax*<br/>
Komut KIMLIĞI aralığının bitiş dizini.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesnesinden cmdIDMin ve cmdIDMax tarafından belirtilen komut kimlikleriyle eşlenmiş bir kullanıcı arabirimi komut ileti işleyicileri grubunu kaldırır.

## <a name="removecommanduihandler"></a>ICommandSource:: RemoveCommandUIHandler

Bir komut kaynak nesnesinden bir kullanıcı arabirimi komut iletisi işleyicisini kaldırır.

```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut KIMLIĞI.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesnesinden cmdID ile eşlenen kullanıcı arabirimi komut iletisi işleyicisini kaldırır.

## <a name="sendcommand"></a>ICommandSource:: SendCommand

Bir ileti gönderir ve döndürmeden önce işlenmesini bekler.

```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*komutundaki*<br/>
Gönderilecek iletinin komut KIMLIĞI.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut tarafından belirtilen KIMLIĞE eşlenen iletiyi eşzamanlı olarak gönderir. İletiyi pencerenin ileti kuyruğuna yerleştirmek için CWnd:: SendMessage çağırır ve bu pencere yordamı döndürmeden önce iletiyi işleyene kadar bekler.
## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandTarget Arabirimi](../../mfc/reference/icommandtarget-interface.md)
