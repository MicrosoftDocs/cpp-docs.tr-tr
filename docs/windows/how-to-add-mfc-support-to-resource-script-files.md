---
title: 'Nasıl yapılır: kaynak betik dosyalarına (C++) için MFC desteği ekleme'
ms.date: 11/04/2016
f1_keywords:
- vc.resvw.add.MFC
helpviewer_keywords:
- rc files [C++], adding MFC support
- .rc files [C++], adding MFC support
- MFC, adding support to resource scripts files
- resource script files [C++], adding MFC support
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
ms.openlocfilehash: c2d0f9ee30085bd2bcc02cf48fd18f6de63eb69a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594395"
---
# <a name="how-to-add-mfc-support-to-resource-script-files-c"></a>Nasıl yapılır: kaynak betik dosyalarına (C++) için MFC desteği ekleme

Normalde, Windows kullanmaya yönelik bir MFC uygulaması oluşturduğunuzda [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md), Microsoft Foundation'ın temel özelliklerini içeren temel bir kümesi (kaynak betiği (.rc) dosyası da dahil olmak üzere) dosyaları sihirbaz oluşturur sınıfları (MFC). Ancak, MFC'ye dayalı olmayan bir Windows uygulaması için bir .rc dosyasını düzenliyorsanız MFC çerçevesine özgü aşağıdaki özellikler kullanılabilir değildir:

- MFC kodu sihirbazları

- Menü komut istemi dizeleri

- Birleşik giriş kutusu denetimleri için Liste içeriği

- ActiveX denetimi barındırma

Ancak sahip olmayan var olan .rc dosyalarına MFC desteği ekleyebilirsiniz.

### <a name="to-add-mfc-support-to-rc-files"></a>.Rc dosyalarına MFC desteği eklemek için

1. Kaynak betik dosyasını açın.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde [kaynak görünümü](../windows/resource-view-window.md), (örneğin, MFC.rc) kaynaklar klasörünü vurgulayın.

3. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ayarlayın **MFC modu** özelliğini **True**.

   > [!NOTE]
   > Bu bayrağı ayarlamanın yanı sıra .rc dosyası bir MFC projesinin bir parçası olmalıdır. Örneğin, yalnızca ayarlamak **MFC modu** için **True** bir .rc dosyasının bir Win32 Proje MFC özelliklerinden hiçbirini size olmaz.

## <a name="requirements"></a>Gereksinimler

MFC

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)