# $NetBSD: Makefile,v 1.6 2011/10/11 19:20:13 joerg Exp $

.include <bsd.own.mk>

PROG=		mandoc

SRCS=		chars.c main.c out.c tree.c \
		eqn_html.c eqn_term.c \
		html.c man_html.c mdoc_html.c tbl_html.c \
		man_term.c mdoc_term.c term.c term_ascii.c \
		term_ps.c tbl_term.c

.ifndef HOSTPROG
DPADD+= 	${MDOCMLLIB.mandoc}
LDADD+= 	-L${MDOCMLOBJDIR.mandoc} -lmandoc
.else
SRCS.libmandoc!=cd ${.PARSEDIR}/../../lib/libmandoc && ${MAKE} -V '$${SRCS}'

SRCS+=		${SRCS.libmandoc}
.endif

.include <bsd.prog.mk>
