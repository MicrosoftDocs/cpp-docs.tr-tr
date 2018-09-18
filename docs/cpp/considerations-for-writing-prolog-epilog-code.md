---
title: Giriş ve bitiş kodu yazmada dikkat edilmesi gerekenler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8cb66865d40e101f951b64aef07c0bb312f91611
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117575"
---
# <a name="considerations-for-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazmada Dikkat Edilmesi Gerekenler

**Microsoft'a özgü**

Kendi giriş ve sonuç kod dizilerinizi yazmadan önce, yığın çerçevesinin nasıl düzenlendiğini anlamak önemlidir. Nasıl kullanılacağını bilmek yararlıdır `__LOCAL_SIZE` simgesi.

##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a> Yığın çerçevesi düzeni

Bu örnekte, 32 bit işlevinde görünebilecek standart giriş kodu gösterilmektedir:

```
push        ebp                ; Save ebp
mov         ebp, esp           ; Set stack frame pointer
sub         esp, localbytes    ; Allocate space for locals
push        <registers>        ; Save registers
```

`localbytes` değişkeni yerel değişkenler için yığında gereken bayt sayısını gösterir, `<registers>` değişkeni ise yığında kaydedilecek yazmaçların listesini gösteren bir yer tutucudur. Yazmaçları gönderdikten sonra, yığın üzerine başka bir uygun veri yerleştirebilirsiniz. Aşağıda ilgili sonuç kodu bulunmaktadır:

```
pop         <registers>   ; Restore registers
mov         esp, ebp      ; Restore stack pointer
pop         ebp           ; Restore ebp
ret                       ; Return from function
```

Yığın her zaman aşağı doğru (yüksek bellek adreslerinden düşük olanlara) büyür. Taban işaretçisi (`ebp`) `ebp`'nin gönderilen değerine işaret eder. Yerel alan başlangıcı `ebp-4`. Yerel değişkenlere erişmek için uygun değeri `ebp`'den çıkararak `ebp`'den bir uzaklık hesaplayın.

##  <a name="_pluslang___local_size"></a> __LOCAL_SIZE

Derleyici, bir simge sağlar `__LOCAL_SIZE`, işlev giriş kodunun satır içi assembler bloğunu kullanmak için. Bu simge, özel giriş kodundaki yığın çerçevesinde yerel değişkenler için alan ayırmak için kullanılır.

Derleyici değeri belirler `__LOCAL_SIZE`. Değerini bayt tüm kullanıcı tanımlı yerel değişkenlerin ve derleyici tarafından oluşturulan geçici değişkenlerin toplam sayısıdır. `__LOCAL_SIZE` yalnızca bir anlık işlenen kullanılabilir. bir ifadede kullanılamaz. Değiştirmemeli veya değeri bu simgeyi yeniden tanımlama. Örneğin:

```
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov        eax, [ebp - __LOCAL_SIZE]   ;Error
```

Aşağıdaki özel giriş ve sonuç içeren çıplak bir işlev örneği kullanan dizilerinin `__LOCAL_SIZE` sembol giriş dizisinde:

```
// the__local_size_symbol.cpp
// processor: x86
__declspec ( naked ) int main() {
   int i;
   int j;

   __asm {      /* prolog */
      push   ebp
      mov      ebp, esp
      sub      esp, __LOCAL_SIZE
      }

   /* Function body */
   __asm {   /* epilog */
      mov      esp, ebp
      pop      ebp
      ret
      }
}
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)