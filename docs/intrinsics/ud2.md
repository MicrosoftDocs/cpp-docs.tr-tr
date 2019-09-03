---
title: __ud2
ms.date: 09/02/2019
f1_keywords:
- __ud2
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
ms.openlocfilehash: b5aa20804099af4d75dcc62a5e62ccc0d4a09566
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219763"
---
# <a name="__ud2"></a>__ud2

**Microsoft 'a özgü**

Tanımsız bir yönerge üretir.

## <a name="syntax"></a>Sözdizimi

```C
void __ud2();
```

## <a name="remarks"></a>Açıklamalar

Tanımlanmamış bir yönerge çalıştırırsanız, işlemci geçersiz bir Opcode özel durumu oluşturur.

`__ud2` İşlevi `UD2` makine yönergesine eşdeğerdir ve yalnızca çekirdek modunda kullanılabilir. Daha fazla bilgi için belgeyi arayın, "Intel mimarisi yazılım geliştiricisi El Ile, birim 2: Yönerge kümesi başvurusu, " [Intel Corporation](https://software.intel.com/articles/intel-sdm) sitesinde.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`__ud2`|x86, x64|

**Üst bilgi dosyası** \<Intrin. h >

**SON Microsoft 'a özgü**

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir özel durum harekete geçiren tanımsız bir yönerge yürütür. Ardından, özel durum işleyicisi, dönüş kodunu sıfırdan bir olarak değiştirir.

```cpp
// __ud2_intrinsic.cpp
#include <stdio.h>
#include <intrin.h>
#include <excpt.h>
// compile with /EHa

int main() {

// Initialize the return code to 0.
int ret = 0;

// Attempt to execute an undefined instruction.
  printf("Before __ud2(). Return code = %d.\n", ret);
  __try {
  __ud2();
  }

// Catch any exceptions and set the return code to 1.
  __except(EXCEPTION_EXECUTE_HANDLER){
  printf("  In the exception handler.\n");
  ret = 1;
  }

// Report the value of the return code.
  printf("After __ud2().  Return code = %d.\n", ret);
  return ret;
}
```

```Output
Before __ud2(). Return code = 0.
  In the exception handler.
After __ud2().  Return code = 1.
```

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
