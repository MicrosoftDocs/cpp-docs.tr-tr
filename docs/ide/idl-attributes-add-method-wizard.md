---
title: IDL Öznitelikleri, Yöntem Ekleme Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.method.idlattrib
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
ms.openlocfilehash: 073f821d7db0733c89c21ed4b2a85014aa151244
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615793"
---
# <a name="idl-attributes-add-method-wizard"></a>IDL Öznitelikleri, Yöntem Ekleme Sihirbazı

Yöntem için arabirim tanımlama dili (IDL) ayarlarını belirtmek için bu sayfanın bir yöntem Ekleme Sihirbazı'nı kullanın.

- **id**

   Yükleme yöntemini tanımlayan sayısal bir kimlik ayarlar. Bkz: [kimliği](/windows/desktop/Midl/id) içinde *MIDL başvuru*.

   Bu kutu özel arabirimler için kullanılamaz ve MFC görüntüleme için kullanılamıyor.

- **call_as**

   Bu yerel yöntemi eşlenebilir uzak bir yöntem adını belirtir. Bkz: [call_as](/windows/desktop/Midl/call-as) içinde *MIDL başvuru*.

   MFC görüntüleme için kullanılamaz.

- **helpcontext**

   Yardım dosyasında bu yöntem kullanıcı görünümü bilgi sağlayan bir bağlam kimliği belirtir. Bkz: [helpcontext](/windows/desktop/Midl/helpcontext) içinde *MIDL başvuru*.

   MFC görüntüleme için kullanılamaz.

- **helpstring**

   Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir. Varsayılan olarak ayarlanmış "yöntemi *yöntem adı*." Bkz: [helpstring](/windows/desktop/Midl/helpstring) içinde *MIDL başvuru*.

   MFC görüntüleme için kullanılamaz.

- **Ek öznitelikler**

   MFC görüntüleme için kullanılamaz.

   |Öznitelik|Açıklama|
   |---------------|-----------------|
   |**hidden**|Yöntem var ancak kullanıcıya dayalı tarayıcıda görüntülenmemesi gerektiğini belirtir. Bkz: [gizli](/windows/desktop/Midl/hidden) içinde *MIDL başvuru*.|
   |**source**|Bir olay kaynağı yöntemi üyesi olduğunu gösterir. Bkz: [kaynak](/windows/desktop/Midl/source) içinde *MIDL başvuru*.|
   |`local`|MIDL derleyicisine yöntemi uzak olmadığını belirtir. Bkz: [yerel](/windows/desktop/Midl/local) içinde *MIDL başvuru*.|
   |**restricted**|Yöntemi rasgele çağrılamaz belirtir. Bkz: [kısıtlı](/windows/desktop/Midl/restricted) içinde *MIDL başvuru*.|
   |**vararg**|Yöntemi, değişken sayıda bağımsız değişken aldığını belirtir. Bunu yapmak için son bağımsız değişken bir güvenli dizisi olmalıdır **değişken** kalan tüm bağımsız değişkenleri içeren bir tür. Bkz: [vararg](/windows/desktop/Midl/vararg) içinde *MIDL başvuru*.|

## <a name="see-also"></a>Ayrıca Bkz.

[Yöntem ekleme](../ide/adding-a-method-visual-cpp.md)<br>
[Yöntem Ekleme Sihirbazı](../ide/add-method-wizard.md)