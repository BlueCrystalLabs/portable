# $OpenBSD: Makefile,v 1.33 2016/03/30 06:38:43 jmc Exp $

.include <bsd.own.mk>		# for NOMAN

POD2MAN=pod2man --official --release="OpenBSD ${OSREV}" --center=OpenSSL

.ifndef NOMAN
MAN=	\
	BIO_f_ssl.3 \
	SSL_CIPHER_get_name.3 \
	SSL_COMP_add_compression_method.3 \
	SSL_CTX_add_extra_chain_cert.3 \
	SSL_CTX_add_session.3 \
	SSL_CTX_ctrl.3 \
	SSL_CTX_flush_sessions.3 \
	SSL_CTX_free.3 \
	SSL_CTX_get_ex_new_index.3 \
	SSL_CTX_get_verify_mode.3 \
	SSL_CTX_load_verify_locations.3 \
	SSL_CTX_new.3 \
	SSL_CTX_sess_number.3 \
	SSL_CTX_sess_set_cache_size.3 \
	SSL_CTX_sess_set_get_cb.3 \
	SSL_CTX_sessions.3 \
	SSL_CTX_set_cert_store.3 \
	SSL_CTX_set_cert_verify_callback.3 \
	SSL_CTX_set_cipher_list.3 \
	SSL_CTX_set_client_CA_list.3 \
	SSL_CTX_set_client_cert_cb.3 \
	SSL_CTX_set_default_passwd_cb.3 \
	SSL_CTX_set_generate_session_id.3 \
	SSL_CTX_set_info_callback.3 \
	SSL_CTX_set_max_cert_list.3 \
	SSL_CTX_set_mode.3 \
	SSL_CTX_set_msg_callback.3 \
	SSL_CTX_set_options.3 \
	SSL_CTX_set_psk_client_callback.3 \
	SSL_CTX_set_quiet_shutdown.3 \
	SSL_CTX_set_session_cache_mode.3 \
	SSL_CTX_set_session_id_context.3 \
	SSL_CTX_set_ssl_version.3 \
	SSL_CTX_set_timeout.3 \
	SSL_CTX_set_tmp_dh_callback.3 \
	SSL_CTX_set_tmp_rsa_callback.3 \
	SSL_CTX_set_verify.3 \
	SSL_CTX_use_certificate.3 \
	SSL_CTX_use_psk_identity_hint.3 \
	SSL_SESSION_free.3 \
	SSL_SESSION_get_ex_new_index.3 \
	SSL_SESSION_get_time.3 \
	SSL_accept.3 \
	SSL_alert_type_string.3 \
	SSL_clear.3 \
	SSL_connect.3 \
	SSL_do_handshake.3 \
	SSL_free.3 \
	SSL_get_SSL_CTX.3 \
	SSL_get_ciphers.3 \
	SSL_get_client_CA_list.3 \
	SSL_get_current_cipher.3 \
	SSL_get_default_timeout.3 \
	SSL_get_error.3 \
	SSL_get_ex_data_X509_STORE_CTX_idx.3 \
	SSL_get_ex_new_index.3 \
	SSL_get_fd.3 \
	SSL_get_peer_cert_chain.3 \
	SSL_get_peer_certificate.3 \
	SSL_get_psk_identity.3 \
	SSL_get_rbio.3 \
	SSL_get_session.3 \
	SSL_get_verify_result.3 \
	SSL_get_version.3 \
	SSL_library_init.3 \
	SSL_load_client_CA_file.3 \
	SSL_new.3 \
	SSL_pending.3 \
	SSL_read.3 \
	SSL_rstate_string.3 \
	SSL_session_reused.3 \
	SSL_set_bio.3 \
	SSL_set_connect_state.3 \
	SSL_set_fd.3 \
	SSL_set_session.3 \
	SSL_set_shutdown.3 \
	SSL_set_verify_result.3 \
	SSL_shutdown.3 \
	SSL_state_string.3 \
	SSL_want.3 \
	SSL_write.3 \
	d2i_SSL_SESSION.3 \
	ssl.3 \

.include <bsd.man.mk>
.else
maninstall:

.endif

.PATH: ${.CURDIR}/../doc
.SUFFIXES: .pod .1 .3 .7
.for sect in 1 3 7
.pod.${sect}:
	@echo '${POD2MAN} --section=${sect} --name=${*:U} $< > $@'
	@${POD2MAN} --section=${sect} --name=${*:U} $< > $@.tmp && mv $@.tmp $@
.endfor

.include <bsd.obj.mk>
.include <bsd.subdir.mk>

clean cleandir:
	rm -f ${MAN}
