---
title: Yönergeler Başvurusu
ms.date: 08/30/2018
f1_keywords:
- Directives Reference
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), directives reference
ms.assetid: da6efcd1-18f7-41de-81cd-a002a02f9a22
ms.openlocfilehash: 655c177b8e5b859faf3b6d9c3250bc3ced31b430
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62178944"
---
# <a name="directives-reference"></a>Yönergeler Başvurusu

## <a name="x64"></a>X64

||||
|-|-|-|
|[.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)|[.ENDPROLOG](../../assembler/masm/dot-endprolog.md)|[PROC](../../assembler/masm/proc.md)|
|[.PUSHFRAME](../../assembler/masm/dot-pushframe.md)|[.PUSHREG](../../assembler/masm/dot-pushreg.md)|[.SAVEREG](../../assembler/masm/dot-savereg.md)|
|[.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)|[.SETFRAME](../../assembler/masm/dot-setframe.md)||

### <a name="code-labels"></a>Kod etiketleri

|||
|-|-|
|[ALIGN](../../assembler/masm/align-masm.md)|[EVEN](../../assembler/masm/even.md)|
|[ETİKET](../../assembler/masm/label-masm.md)|[ORG](../../assembler/masm/org.md)|

### <a name="conditional-assembly"></a>Koşullu derleme

||||
|-|-|-|
|[ELSE](../../assembler/masm/else-masm.md)|[ELSEIF](../../assembler/masm/elseif-masm.md)|[ELSEIF2](../../assembler/masm/elseif2.md)|
|[IF](../../assembler/masm/if-masm.md)|[IF2](../../assembler/masm/if2.md)|[IFB](../../assembler/masm/ifb.md)/[IFNB](../../assembler/masm/ifnb.md)|
|[IFDEF](../../assembler/masm/ifdef.md)/[IFNDEF](../../assembler/masm/ifndef.md)|[IFDIF](../../assembler/masm/ifdif.md)/[IFDIF&AMP;#91;&AMP;#91;EDİYORUM&AMP;#93;&AMP;#93;](../../assembler/masm/ifdif.md)|[IFE](../../assembler/masm/ife.md)|
|[IFIDN](../../assembler/masm/ifidn.md)/[IFIDN&AMP;#91;&AMP;#91;EDİYORUM&AMP;#93;&AMP;#93;](../../assembler/masm/ifidn.md)|||

### <a name="conditional-control-flow"></a>Koşullu denetim akışı

||||
|-|-|-|
|[.BREAK](../../assembler/masm/dot-break.md)|[.CONTINUE](../../assembler/masm/dot-continue.md)|[.ELSE](../../assembler/masm/dot-else.md)|
|[.ELSEIF](../../assembler/masm/dot-if.md)|[.ENDIF](../../assembler/masm/dot-endif.md)|[.ENDW](../../assembler/masm/dot-endw.md)|
|[.IF](../../assembler/masm/dot-if.md)|[.REPEAT](../../assembler/masm/dot-repeat.md)|[.UNTIL](../../assembler/masm/dot-until.md)|
|[.UNTILCXZ](../../assembler/masm/dot-untilcxz.md)|[.WHILE](../../assembler/masm/dot-while.md)||

### <a name="conditional-error"></a>Koşullu hata

||||
|-|-|-|
|[.ERR](../../assembler/masm/dot-err.md)|[.ERR2](../../assembler/masm/dot-err2.md)|[.ERRB](../../assembler/masm/dot-errb.md)|
|[.ERRDEF](../../assembler/masm/dot-errdef.md)|[. ERRDIF](../../assembler/masm/dot-errdif.md)/[. ERRDIF&AMP;#91;&AMP;#91;EDİYORUM&AMP;#93;&AMP;#93;&AMP;#93;](../../assembler/masm/dot-errdif.md)|[.ERRE](../../assembler/masm/dot-erre.md)|
|[. ERRIDN](../../assembler/masm/dot-erridn.md)/[. ERRIDN&AMP;#91;&AMP;#91;EDİYORUM&AMP;#93;&AMP;#93;](../../assembler/masm/dot-erridn.md)|[.ERRNB](../../assembler/masm/dot-errnb.md)|[.ERRNDEF](../../assembler/masm/dot-errndef.md)|
|[.ERRNZ](../../assembler/masm/dot-errnz.md)|||

### <a name="data-allocation"></a>Veri ayırma

||||
|-|-|-|
|[ALIGN](../../assembler/masm/align-masm.md)|[BAYT](../../assembler/masm/byte-masm.md)/[SBYTE](../../assembler/masm/sbyte-masm.md)|[DWORD](../../assembler/masm/dword.md)/[SDWORD](../../assembler/masm/sdword.md)|
|[EVEN](../../assembler/masm/even.md)|[FWORD](../../assembler/masm/fword.md)|[ETİKET](../../assembler/masm/label-masm.md)|
|[ORG](../../assembler/masm/org.md)|[QWORD](../../assembler/masm/qword.md)|[REAL4](../../assembler/masm/real4.md)|
|[REAL8](../../assembler/masm/real8.md)|[REAL10](../../assembler/masm/real10.md)|[TBYTE](../../assembler/masm/tbyte.md)|
|[WORD](../../assembler/masm/word.md)/[SWORD](../../assembler/masm/sword.md)|||

### <a name="equates"></a>Karşılık gelir

||||
|-|-|-|
|[=](../../assembler/masm/equal.md)|[EQU](../../assembler/masm/equ.md)|[TEXTEQU](../../assembler/masm/textequ.md)|

### <a name="listing-control"></a>Denetim listesi

||||
|-|-|-|
|[.CREF](../../assembler/masm/dot-cref.md)|[.LIST](../../assembler/masm/dot-list.md)|[.LISTALL](../../assembler/masm/dot-listall.md)|
|[.LIST](../../assembler/masm/dot-listif.md)|[.LISTMACRO](../../assembler/masm/dot-listmacro.md)|[.LISTMACROALL](../../assembler/masm/dot-listmacroall.md)|
|[.NOCREF](../../assembler/masm/dot-nocref.md)|[.NOLIST](../../assembler/masm/dot-nolist.md)|[.NOLISTIF](../../assembler/masm/dot-nolistif.md)|
|[.NOLISTMACRO](../../assembler/masm/dot-nolistmacro.md)|[PAGE](../../assembler/masm/page.md)|[SUBTITLE](../../assembler/masm/subtitle.md)|
|[.TFCOND](../../assembler/masm/dot-tfcond.md)|[TITLE](../../assembler/masm/title.md)||

### <a name="macros"></a>Makrolar

||||
|-|-|-|
|[ENDM](../../assembler/masm/endm.md)|[EXITM](../../assembler/masm/exitm.md)|[GİT](../../assembler/masm/goto-masm.md)|
|[YEREL](../../assembler/masm/local-masm.md)|[MACRO](../../assembler/masm/macro.md)|[PURGE](../../assembler/masm/purge.md)|

### <a name="miscellaneous"></a>Çeşitli

||||
|-|-|-|
|[DİĞER AD](../../assembler/masm/alias-masm.md)|[ASSUME](../../assembler/masm/assume.md)|[AÇIKLAMA](../../assembler/masm/comment-masm.md)|
|[ECHO](../../assembler/masm/echo.md)|[SON](../../assembler/masm/end-masm.md)|[.FPO](../../assembler/masm/dot-fpo.md)|
|[İÇERİR](../../assembler/masm/include-masm.md)|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[MMWORD](../../assembler/masm/mmword.md)|
|[SEÇENEĞİ](../../assembler/masm/option-masm.md)|[POPCONTEXT](../../assembler/masm/popcontext.md)|[PUSHCONTEXT](../../assembler/masm/pushcontext.md)|
|[.RADIX](../../assembler/masm/dot-radix.md)|[.SAFESEH](../../assembler/masm/dot-safeseh.md)|[XMMWORD](../../assembler/masm/xmmword.md)|
|[YMMWORD](../../assembler/masm/ymmword.md)|||

### <a name="procedures"></a>Yordamlar

||||
|-|-|-|
|[ENDP](../../assembler/masm/endp.md)|[INVOKE](../../assembler/masm/invoke.md)|[PROC](../../assembler/masm/proc.md)|
|[PROTO](../../assembler/masm/proto.md)|||

### <a name="processor"></a>İşlemci

||||
|-|-|-|
|[.386](../../assembler/masm/dot-386.md)|[.386P](../../assembler/masm/dot-386p.md)|[.387](../../assembler/masm/dot-387.md)|
|[.486](../../assembler/masm/dot-486.md)|[.486P](../../assembler/masm/dot-486p.md)|[.586](../../assembler/masm/dot-586.md)|
|[.586P](../../assembler/masm/dot-586p.md)|[.686](../../assembler/masm/dot-686.md)|[.686P](../../assembler/masm/dot-686p.md)|
|[.K3D](../../assembler/masm/dot-k3d.md)|[.MMX](../../assembler/masm/dot-mmx.md)|[.XMM](../../assembler/masm/dot-xmm.md)|

### <a name="repeat-blocks"></a>Blokları yineleyin

||||
|-|-|-|
|[ENDM](../../assembler/masm/endm.md)|[İÇİN](../../assembler/masm/for-masm.md)|[FORC](../../assembler/masm/forc.md)|
|[GİT](../../assembler/masm/goto-masm.md)|[REPEAT](../../assembler/masm/repeat.md)|[WHILE](../../assembler/masm/while-masm.md)|

### <a name="scope"></a>Kapsam

||||
|-|-|-|
|[COMM](../../assembler/masm/comm.md)|[EXTERN](../../assembler/masm/extern-masm.md)|[EXTERNDEF](../../assembler/masm/externdef.md)|
|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[GENEL](../../assembler/masm/public-masm.md)||

### <a name="segment"></a>Segment

||||
|-|-|-|
|[.ALPHA](../../assembler/masm/dot-alpha.md)|[ASSUME](../../assembler/masm/assume.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|
|[SON](../../assembler/masm/end-masm.md)|[SONA ERER](../../assembler/masm/ends-masm.md)|[GROUP](../../assembler/masm/group.md)|
|[SEGMENT](../../assembler/masm/segment.md)|[.SEQ](../../assembler/masm/dot-seq.md)||

### <a name="simplified-segment"></a>Basitleştirilmiş Segment

||||
|-|-|-|
|[.CODE](../../assembler/masm/dot-code.md)|[.CONST](../../assembler/masm/dot-const.md)|[.DATA](../../assembler/masm/dot-data.md)|
|[.DATA?](../../assembler/masm/dot-data-q.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|[.EXIT](../../assembler/masm/dot-exit.md)|
|[.FARDATA](../../assembler/masm/dot-fardata.md)|[.FARDATA?](../../assembler/masm/dot-fardata-q.md)|[.MODEL](../../assembler/masm/dot-model.md)|
|[.STACK](../../assembler/masm/dot-stack.md)|[.STARTUP](../../assembler/masm/dot-startup.md)||

### <a name="string"></a>Dize

|||
|-|-|
|[CATSTR](../../assembler/masm/catstr.md)|[INSTR](../../assembler/masm/instr.md)|
|[SIZESTR](../../assembler/masm/sizestr.md)|[SUBSTR](../../assembler/masm/substr.md)|

### <a name="structure-and-record"></a>Yapı ve kayıt

||||
|-|-|-|
|[SONA ERER](../../assembler/masm/ends-masm.md)|[KAYDI](../../assembler/masm/record-masm.md)|[YAPI](../../assembler/masm/struct-masm.md)|
|[TÜR TANIMI](../../assembler/masm/typedef-masm.md)|[UNION](../../assembler/masm/union.md)||

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Macro Assembler Başvurusu](../../assembler/masm/microsoft-macro-assembler-reference.md)<br/>