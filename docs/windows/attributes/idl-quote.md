---
title: idl_quote (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.idl_quote
dev_langs:
- C++
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 31e06d83ce64675b5b1e8ac9cbb865bfb3eff334
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074169"
---
# <a name="idlquote"></a>idl_quote

Visual C++'ın geçerli sürümünde desteklenmeyen IDL yapıları kullanmanıza olanak tanır ve bunları oluşturulan .idl dosyasına geçirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>Parametreler

*Metin*<br/>
Visual C++ derleyicisi aracılığıyla oluşturulan .idl dosyasına bir derleyici hatası dönmeden iletmek için istediğinize öznitelik adı.

## <a name="remarks"></a>Açıklamalar

Varsa **idl_quote** C++ özniteliği kullanılır (noktalı sağ köşeli ayraç sonra), bir tek başına öznitelik olarak ardından *metin* olduğu gibi birleştirilmiş bir .idl dosyasında yer alır. Varsa **idl_quote** üzerinde bir sembol, kullanılan *metin* sembolün için öznitelik bloğu içinde yer alır.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl desteklenmeyen bir öznitelik belirtebilirsiniz gösterir (kullanarak **içinde**, desteklendiği) ve nasıl tanımlanacağını ve bir tanımsız .idl yapısı kullanın:

```cpp
// cpp_attr_ref_idl_quote.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];

[export]
struct MYFLOT {
   int i;
};

[export]
struct MYDUB {
   int i;
};

[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];

typedef struct _S1_TYPE {
   long l1;

union {
   MYFLOT f1; MYDUB d2; } U1_TYPE;
} S1_TYPE;

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]
__interface IStatic{
   HRESULT Func1([idl_quote("in")] int i);
   HRESULT func( S1_TYPE* myStruct );
};
```

Bu kod neden `MYFLOT` ve `MYDUB` ve *metin* oluşturulan .idl dosyasında yerleştirilecek girişi. *Adı* parametresi zorlar *metin* başvuran hiçbir şey önce yerleştirilecek *adı* oluşturulan .idl dosyasındaki. *Bağımlılıkları* parametre zorlar önce yerleştirilecek bağımlılık liste tanımları *metin* oluşturulan .idl dosyasındaki.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)