---
description: 'Hakkında daha fazla bilgi: giriş/bitiş kodu yazma konuları'
title: Prolog-Epilog kodu yazma konuları
ms.date: 11/04/2016
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
ms.openlocfilehash: 6deb6e9120c83992a7fe2529d0c9366b8e191056
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204777"
---
# <a name="considerations-for-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazmada Dikkat Edilmesi Gerekenler

**Microsoft'a Özgü**

Kendi giriş ve bitiş kodu dizilerini yazmadan önce, yığın çerçevesinin nasıl düzenlendiğini anlamak önemlidir. Ayrıca, simgenin nasıl kullanılacağını öğrenmek de yararlı olur `__LOCAL_SIZE` .

## <a name="stack-frame-layout"></a><a name="_pluslang_c.2b2b_.stack_frame_layout"></a> Yığın çerçevesi düzeni

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

Yığın her zaman aşağı doğru (yüksek bellek adreslerinden düşük olanlara) büyür. Taban işaretçisi (`ebp`) `ebp`'nin gönderilen değerine işaret eder. Yereller alanı tarihinde başlar `ebp-4` . Yerel değişkenlere erişmek için uygun değeri `ebp`'den çıkararak `ebp`'den bir uzaklık hesaplayın.

## <a name="__local_size"></a><a name="_pluslang___local_size"></a> __LOCAL_SIZE

Derleyici, `__LOCAL_SIZE` işlev giriş kodunun satır içi assembler bloğunda kullanılmak üzere bir sembol sağlar. Bu simge, özel giriş kodundaki yığın çerçevesindeki yerel değişkenler için alan ayırmak için kullanılır.

Derleyici değerini belirler `__LOCAL_SIZE` . Değeri, Kullanıcı tanımlı tüm yerel değişkenlerin ve derleyicinin ürettiği geçici değişkenlerin toplam bayt sayısıdır. `__LOCAL_SIZE` yalnızca bir anında işlenen olarak kullanılabilir; bir ifadede kullanılamaz. Bu sembolün değerini değiştirmemelidir veya yeniden tanımlamanız gerekir. Örneğin:

```
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov        eax, [ebp - __LOCAL_SIZE]   ;Error
```

Özel giriş ve bitiş dizileri içeren bir çıplak işlevin aşağıdaki örneği, `__LOCAL_SIZE` giriş sırasındaki sembolü kullanır:

```cpp
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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Naked Işlev çağrıları](../cpp/naked-function-calls.md)
