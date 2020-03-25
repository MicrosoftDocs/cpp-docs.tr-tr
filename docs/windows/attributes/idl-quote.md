---
title: idl_quote (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_quote
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
ms.openlocfilehash: 4b05da6d237d71e0cc645ad0f626f75ecd85c827
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168035"
---
# <a name="idl_quote"></a>idl_quote

Geçerli Visual C++ sürümünde desteklenmeyen IDL yapılarını kullanmanıza ve bunların oluşturulan. IDL dosyasına geçmesini sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>Parametreler

*metinleri*<br/>
Microsoft C++ derleyicisini bir derleyici hatası döndürmeden oluşturulan. IDL dosyasına geçireplanladığınız öznitelik adı.

## <a name="remarks"></a>Açıklamalar

**İdl_quote** C++ özniteliği tek başına bir öznitelik olarak kullanılırsa (kapatma parantezinden sonra noktalı virgül ile), *metin* birleştirilmiş. IDL dosyasına olduğu gibi yerleştirilir. Bir sembol üzerinde **İdl_quote** kullanılırsa, *metin* söz konusu simgenin öznitelik bloğunun içine yerleştirilir.

## <a name="example"></a>Örnek

Aşağıdaki kod, desteklenmeyen bir özniteliği (desteklenen ' **de**kullanarak) ve tanımsız bir. IDL yapısını nasıl tanımlanacağını ve kullanacağınızı gösterir:

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

Bu kod, `MYFLOT` ve `MYDUB` ve *metin* girişinin oluşturulan. IDL dosyasına yerleştirilmesini sağlar. *Name* parametresi, oluşturulan. IDL dosyasındaki *adı* başvuruda bulunan her şeyin önüne konacak *metni* zorlar. *Dependencies* parametresi, bağımlılık listesi tanımlarını oluşturulan. IDL dosyasındaki *metinden* önce yerleştirilecek şekilde zorlar.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)
