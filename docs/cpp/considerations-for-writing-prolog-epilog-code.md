---
title: Prolog-Epilog Kodu Yazmak İçin Dikkat Edilecek Noktalar
ms.date: 11/04/2016
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
ms.openlocfilehash: cda6a6c82efcf30a916aced121024095d7ce8138
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337106"
---
# <a name="considerations-for-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazmada Dikkat Edilmesi Gerekenler

**Microsoft'a Özgü**

Kendi prolog ve epilog kod dizileri yazmadan önce, yığın çerçeve nasıl ortaya konulmuştur anlamak önemlidir. Sembolün nasıl kullanılacağını `__LOCAL_SIZE` bilmek de yararlıdır.

## <a name="stack-frame-layout"></a><a name="_pluslang_c.2b2b_.stack_frame_layout"></a>Yığın Çerçeve Düzeni

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

Yığın her zaman aşağı doğru (yüksek bellek adreslerinden düşük olanlara) büyür. Taban işaretçisi (`ebp`) `ebp`'nin gönderilen değerine işaret eder. Yerel alan . `ebp-4` Yerel değişkenlere erişmek için uygun değeri `ebp`'den çıkararak `ebp`'den bir uzaklık hesaplayın.

## <a name="__local_size"></a><a name="_pluslang___local_size"></a>__LOCAL_SIZE

Derleyici, `__LOCAL_SIZE`işlev prolog kodunun satır satır ara derleyici bloğunda kullanılmak üzere bir sembol sağlar. Bu sembol, özel prolog kodunda yığın çerçevesindeki yerel değişkenler için alan ayırmak için kullanılır.

`__LOCAL_SIZE`Derleyici. Değeri, kullanıcı tarafından tanımlanan tüm yerel değişkenlerin ve derleyici tarafından oluşturulan geçici değişkenlerin toplam bayt sayısıdır. `__LOCAL_SIZE`sadece ani bir operand olarak kullanılabilir; bir ifadede kullanılamaz. Bu sembolün değerini değiştirmemeniz veya yeniden tanımlamamalısınız. Örneğin:

```
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov        eax, [ebp - __LOCAL_SIZE]   ;Error
```

Özel prolog ve epilog dizileri içeren çıplak bir `__LOCAL_SIZE` işlevaşağıdaki örnek prolog dizisinde sembolü kullanır:

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

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Çıplak İşlev Çağrıları](../cpp/naked-function-calls.md)
