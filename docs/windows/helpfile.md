---
title: HelpFile | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpfile
dev_langs:
- C++
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 66cd89c28ea01c3a75d0cb25aa6f96a234e379b2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418209"
---
# <a name="helpfile"></a>helpfile

Bir tür kitaplığı için Yardım dosyasına adını ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpfile(
   "filename"
) ]
```

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Yardım konuları içeren dosyanın adı.

## <a name="remarks"></a>Açıklamalar

**Helpfile** C++ özniteliği ile aynı işlevlere sahip [helpfile](/windows/desktop/Midl/helpfile) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [Modülü](../windows/module-cpp.md) nasıl kullanılacağına ilişkin bir örnek **helpfile**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**arabirimi**, **typedef**, **sınıfı**, yöntemi **özelliği**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Arabirim Öznitelikleri](../windows/interface-attributes.md)<br/>
[Sınıf Öznitelikleri](../windows/class-attributes.md)<br/>
[Yöntem Öznitelikleri](../windows/method-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](../windows/helpcontext.md)<br/>
[helpstring](../windows/helpstring.md)  