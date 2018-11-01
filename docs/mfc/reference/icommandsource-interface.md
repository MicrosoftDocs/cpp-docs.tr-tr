---
title: ICommandSource arabirimi
ms.date: 11/04/2016
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
ms.openlocfilehash: 4fca5a2ffef7e8da4f6dd79fcd99c72e92cfdf6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538443"
---
# <a name="icommandsource-interface"></a>ICommandSource arabirimi

Bir kullanıcı denetimine komut kaynak nesneden gönderilen komutları yönetir.

## <a name="syntax"></a>Sözdizimi

```
interface class ICommandSource
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ICommandSource::AddCommandHandler](#addcommandhandler)|Bir komut işleyici, bir komut kaynak nesnesine ekler.|
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|Komut işleyicileri grubu, bir komut kaynak nesnesine ekler.|
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|Bir grup kullanıcı arabirimi komut ileti işleyicileri, bir komut kaynak nesnesine ekler.|
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|Bir kullanıcı arabirimi komut ileti işleyicisi komut kaynak nesnesine ekler.|
|[ICommandSource::PostCommand](#postcommand)|İşlenmesi için beklemenize gerek kalmadan bir ileti gönderir.|
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|Bir komut işleyici, bir komut kaynak nesneden kaldırır.|
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|Bir grup komut işleyicileri komut kaynak nesnesinden kaldırır.|
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|Bir grup kullanıcı arabirimi komut ileti işleyicileri komut kaynak nesnesinden kaldırır.|
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|Bir kullanıcı arabirimi komut ileti işleyicisi komut kaynak nesnesinden kaldırır.|
|[ICommandSource::SendCommand](#sendcommand)|Bir ileti gönderir ve döndürmeden önce işlenecek bekler.|

### <a name="remarks"></a>Açıklamalar

MFC görünümü, bir kullanıcı denetiminde barındırdığınızda [CWinFormsView sınıfı](../../mfc/reference/cwinformsview-class.md) yollar komutları ve güncelleştirme komut UI iletilerini MFC komutlarını (örneğin, çerçeve menüsü ögeleri ve araç çubuğu düğmeleri) işlemelerine izin vermek için kullanıcı denetimi için. Uygulayarak [ICommandTarget arabirimi](../../mfc/reference/icommandtarget-interface.md), kullanıcı denetimine bir başvuru size `ICommandSource` nesne.

Bkz [nasıl yapılır: Windows Forms denetimi için komut yönlendirme ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) nasıl kullanılacağına ilişkin bir örnek `ICommandTarget`.

Windows Forms kullanma hakkında daha fazla bilgi için bkz. [MFC içinde Windows formu kullanıcı denetimi kullanma](../../dotnet/using-a-windows-form-user-control-in-mfc.md).

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxwinforms.h (derleme atlmfc\lib\mfcmifc80.dll içinde tanımlanmıştır)

## <a name="addcommandhandler"></a>  ICommandSource::AddCommandHandler

Bir komut işleyici, bir komut kaynak nesnesine ekler.
```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.
*cmdHandler*<br/>
Komut işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut işleyicisi cmdHandler komut kaynak nesnesine ekler ve işleyici için cmdID eşler.
Bkz: [nasıl yapılır: Windows Forms denetimi için komut yönlendirme ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) AddCommandHandler kullanma örneği için.

## <a name="addcommandrangehandler"></a> ICommandSource::AddCommandRangeHandler

Komut işleyicileri grubu, bir komut kaynak nesnesine ekler.
```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut Kimliği aralığın başlangıç dizini.
*cmdIDMax*<br/>
Komut Kimliği aralığı bitiş dizini.
*cmdHandler*<br/>
Komutlar eşlenmiş ileti işleyicisi yöntemi için bir tanıtıcı.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir tek ileti işleyici komut kimlikleri bir aralıkta eşler ve komut kaynak nesnesine ekler. Bu, bir yöntemle ilgili düğmesi grubu işlemek için kullanılır.

## <a name="addcommandrangeuihandler"></a> ICommandSource::AddCommandRangeUIHandler

Bir grup kullanıcı arabirimi komut ileti işleyicileri, bir komut kaynak nesnesine ekler.
```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut Kimliği aralığın başlangıç dizini.
*cmdIDMax*<br/>
Komut Kimliği aralığı bitiş dizini.
*cmdHandler*<br/>
Komutlar eşlenmiş ileti işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir tek bir kullanıcı arabirimi komut ileti işleyicisi komut kimlikleri bir aralıkta eşler ve komut kaynak nesnesine ekler. Bu, bir yöntemle ilgili düğmesi grubu işlemek için kullanılır.

## <a name="addcommanduihandler"></a> ICommandSource::AddCommandUIHandler

Bir kullanıcı arabirimi komut ileti işleyicisi komut kaynak nesnesine ekler.
```
void AddCommandUIHandler(
    unsigned int cmdID,
    CommandUIHandler^ cmdUIHandler);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.
*cmdUIHandler*<br/>
Kullanıcı arabirimi komut ileti işleyicisi yöntemi için bir tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcı arabirimi komut ileti işleyicisi cmdHandler komut kaynak nesnesine ekler ve işleyici için cmdID eşler.

## <a name="postcommand"></a> ICommandSource::PostCommand

İşlenmesi için beklemenize gerek kalmadan bir ileti gönderir.
```
void PostCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*Komutu*<br/>
Yayımlanacak ileti komut kimliği.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, zaman uyumsuz olarak komutu tarafından belirtilen kimliği eşlenen bir ileti gönderir. Bu pencerenin ileti kuyrukta bir ileti yerleştirmek için CWnd::PostMessage çağıracak ve sonra iletiyi işlemek karşılık gelen penceresi için beklemenize gerek kalmadan.

## <a name="removecommandhandler"></a> ICommandSource::RemoveCommandHandler

Bir komut işleyici, bir komut kaynak nesneden kaldırır.
```
void RemoveCommandHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.
### <a name="remarks"></a>Açıklamalar

Bu yöntem komut kaynak nesneden cmdID için eşlenmiş komut işleyici kaldırır.

## <a name="removecommandrangecommandhandler"></a> ICommandSource::RemoveCommandRangeHandler

Bir grup komut işleyicileri komut kaynak nesnesinden kaldırır.
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut Kimliği aralığın başlangıç dizini.
*cmdIDMax*<br/>
Komut Kimliği aralığı bitiş dizini.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir grup için komut kimlikleri belirtilen komut kaynak nesneden cmdIDMax, cmdIDMin ile eşlenmiş ileti işleyicilerini kaldırır.

## <a name="removecommandrangeuihandler"></a> ICommandSource::RemoveCommandRangeUIHandler

Bir grup kullanıcı arabirimi komut ileti işleyicileri komut kaynak nesnesinden kaldırır.
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```

### <a name="parameters"></a>Parametreler

*cmdIDMin*<br/>
Komut Kimliği aralığın başlangıç dizini.
*cmdIDMax*<br/>
Komut Kimliği aralığı bitiş dizini.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir grup için komut kimlikleri belirtilen komut kaynak nesneden cmdIDMin ve cmdIDMax, eşlenen kullanıcı arabirimi komut ileti işleyicilerini kaldırır.

## <a name="removecommanduihandler"></a> ICommandSource::RemoveCommandUIHandler

Bir kullanıcı arabirimi komut ileti işleyicisi komut kaynak nesnesinden kaldırır.
```
void RemoveCommandUIHandler(unsigned int cmdID);
```

### <a name="parameters"></a>Parametreler

*cmdID*<br/>
Komut kimliği.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, komut kaynak nesneden cmdID için eşlenen kullanıcı arabirimi komut ileti işleyicisini kaldırır.

## <a name="sendcommand"></a> ICommandSource::SendCommand

Bir ileti gönderir ve döndürmeden önce işlenecek bekler.
```
void SendCommand(unsigned int command);
```

### <a name="parameters"></a>Parametreler

*Komutu*<br/>
Gönderilecek iletinin komut kimliği.
### <a name="remarks"></a>Açıklamalar

Bu yöntem, zaman uyumlu olarak komutu tarafından belirtilen kimliği eşlenen bir ileti gönderir. Bu pencerenin ileti kuyrukta bir ileti yerleştirmek için CWnd::SendMessage çağırır ve bu pencere yordamını döndürmeden önce iletiyi işleyene kadar bekler.
## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Windows Forms Denetimi'ne Yönlendiren Komut Ekleme](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)<br/>
[ICommandTarget Arabirimi](../../mfc/reference/icommandtarget-interface.md)
