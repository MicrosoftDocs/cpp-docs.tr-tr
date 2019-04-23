---
title: pointers_to_members
ms.date: 11/04/2016
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragmas, pointers_to_members
- members, pointers to
- pointers_to_members pragma
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
ms.openlocfilehash: 5ee45a77a7094fb1ef9ba536bae391aaad00e812
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032069"
---
# <a name="pointerstomembers"></a>pointers_to_members

**C++ özgü**

Bir sınıf üyesinin işaretçisinin, ilişkilendirilmiş sınıf tanımından önce bildirilip bildirilemeyeceğini ve işaretçi boyutunu ve işaretçiyi yorumlamak için gerekli kodu denetlemek için kullanılıp kullanılmadığını belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )
```

## <a name="remarks"></a>Açıklamalar

Koyabilirsiniz bir **pointers_to_members** pragma kullanmaya alternatif olarak, kaynak dosyanızdaki [/vmx](../build/reference/vmb-vmg-representation-method.md) derleyici seçenekleri veya [devralma anahtar sözcükleri](../cpp/inheritance-keywords.md).

*İşaretçi bildirimi* bağımsız değişkeni, bir işaretçi üye önce veya sonra ilişkilendirilmiş işlev tanımından bildirip bildirmediğinizi belirtir. *İşaretçi bildirimi* bağımsız değişkeni aşağıdaki iki simgeden biridir:

|Bağımsız Değişken|Açıklamalar|
|--------------|--------------|
|*full_generality*|Güvenli, bazen uygun durumda olmayan kod üretir. Kullandığınız *full_generality* herhangi bir üyenin işaretçisi ilişkilendirilmiş sınıf tanımından önce bildirilmişse. Her zaman bu bağımsız değişken tarafından belirtilen işaretçi gösterimini kullanır ve *most-general-representation* bağımsız değişken. /vmg ile eşdeğerdir.|
|*best_case*|Tüm üye işaretçileri için best-case gösterimini kullanılarak güvenli, en iyi durumda kod oluşturur. Sınıfın bir üyesinin işaretçisini bildirmeden önce sınıfın tanımlanmasını gerektirir. Varsayılan değer *best_case*.|

*Most-general-representation* bağımsız değişkeni, derleyicinin güvenli bir şekilde herhangi bir çeviri birimindeki bir sınıfın bir üye işaretçisi başvurmak için kullanabileceğiniz en küçük işaretçi gösterimini belirtir. Bağımsız değişken aşağıdakilerden biri olabilir:

|Bağımsız Değişken|Açıklamalar|
|--------------|--------------|
|*single_inheritance*|En genel gösterim, bir üye işlevi işaretçisi olan single-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli birden çok veya sanal ise hataya neden olur.|
|*birden çok devralma*|En genel gösterim, bir üye işlev işaretçisi olan multiple-inheritance'tır. Kendisi için bir üye işaretçisinin bildirildiği bir sınıf tanımının devralma modeli sanal ise hataya neden olur.|
|*virtual_inheritance*|En genel devralma, bir üye işlev işaretçisi olan virtual-inheritance'tır. Hiçbir zaman hataya neden olmaz. Bu varsayılan bağımsız değişkendir, `#pragma pointers_to_members(full_generality)` kullanılır.|

> [!CAUTION]
> Biz yerleştirmenizi öneri **pointers_to_members** pragmasını yalnızca etkilemek istediğiniz kaynak kod dosyasında ve sonra yerleştirmenizi `#include` yönergeleri. Bu uygulama, pragmanın başka dosyaları etkileme riskini ve aynı değişken, işlev veya sınıf adı için yanlışlıkla birden fazla tanım belirtme olasılığınızı azaltır.

## <a name="example"></a>Örnek

```
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

## <a name="end-c-specific"></a>END C++ özgü

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)