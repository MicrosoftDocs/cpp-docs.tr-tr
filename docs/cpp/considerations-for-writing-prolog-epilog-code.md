---
title: Giriş-bitiş kodu yazma konuları
ms.date: 11/04/2016
helpviewer_keywords:
- stack frame layout
- prolog code
- epilog code
- __LOCAL_SIZE constant
- stack, stack frame layout
ms.assetid: c7814de2-bb5c-4f5f-96d0-bcfd2ad3b182
ms.openlocfilehash: a598ddbdd1b5f91c97e32905202e264b444c05d0
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988696"
---
# <a name="considerations-for-writing-prologepilog-code"></a>Giriş ve Bitiş Kodu Yazmada Dikkat Edilmesi Gerekenler

**Microsoft 'a özgü**

Kendi giriş ve bitiş kodu dizilerini yazmadan önce, yığın çerçevesinin nasıl düzenlendiğini anlamak önemlidir. `__LOCAL_SIZE` sembolünü nasıl kullanacağınızı öğrenmek de yararlı olur.

##  <a name="_pluslang_c.2b2b_.stack_frame_layout"></a>Yığın çerçevesi düzeni

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

Yığın her zaman aşağı doğru (yüksek bellek adreslerinden düşük olanlara) büyür. Taban işaretçisi (`ebp`) `ebp`'nin gönderilen değerine işaret eder. Yereller alanı `ebp-4`başlar. Yerel değişkenlere erişmek için uygun değeri `ebp`'den çıkararak `ebp`'den bir uzaklık hesaplayın.

##  <a name="_pluslang___local_size"></a>__LOCAL_SIZE

Derleyici, işlev giriş kodunun satır içi assembler bloğunda kullanılmak üzere `__LOCAL_SIZE`bir sembol sağlar. Bu simge, özel giriş kodundaki yığın çerçevesindeki yerel değişkenler için alan ayırmak için kullanılır.

Derleyici `__LOCAL_SIZE`değerini belirler. Değeri, Kullanıcı tanımlı tüm yerel değişkenlerin ve derleyicinin ürettiği geçici değişkenlerin toplam bayt sayısıdır. `__LOCAL_SIZE`, yalnızca bir anında işlenen olarak kullanılabilir; bir ifadede kullanılamaz. Bu sembolün değerini değiştirmemelidir veya yeniden tanımlamanız gerekir. Örneğin:

```
mov        eax, __LOCAL_SIZE           ;Immediate operand--Okay
mov        eax, [ebp - __LOCAL_SIZE]   ;Error
```

Özel giriş ve bitiş dizileri içeren bir çıplak işlevin aşağıdaki örneği, giriş sırasındaki `__LOCAL_SIZE` sembolünü kullanır:

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

[Naked İşlevi Çağrıları](../cpp/naked-function-calls.md)
