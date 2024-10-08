# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: rwintgen <rwintgen@student.42.fr>          +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2024/06/26 16:54:24 by rwintgen          #+#    #+#              #
#    Updated: 2024/07/01 12:42:31 by rwintgen         ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

MAKEFLAGS	+=	--no-print-directory

NAME		=	philo
HEADER		=	-I ./include

CC			=	cc
CFLAGS		=	-Werror -Wall -Wextra

SRCS		=	main.c \
				src/data_init.c \
				src/monitoring.c \
				src/parsing.c \
				src/process.c \
				src/utils/utils.c \
				src/utils/functions/ph_atol.c \
				src/utils/functions/ph_itoa.c \
				src/utils/functions/ph_nblen.c \
				src/utils/functions/ph_strjoin.c \
				src/utils/functions/ph_strlen.c \
				src/utils/functions/ph_usleep.c
				
GREEN	=	\033[0;32m
RED		=	\033[0;31m
NC		=	\033[0m

OBJDIR		=	obj
OBJS		=	$(addprefix $(OBJDIR)/, $(SRCS:.c=.o))

all			:	$(NAME)
				@echo "$(GREEN)philo compiled$(NC)"

$(NAME)		:	$(OBJS)
				@clear
				@echo "  __                       "
				@echo " /__)/ '/   _     / _ _  _ "
				@echo "/   /)/(()_) ()/)/)(-/ _)  "
				@echo "              /            "
				@echo "  by rwintgen\n"
				@$(CC) $(CFLAGS) $(OBJS) -o $(NAME)
				@echo "$(GREEN)philo linked$(NC)"

$(OBJDIR)/%.o: %.c
				@mkdir -p $(@D)
				@$(CC) $(HEADER) $(CFLAGS) -c $< -o $@

clean		:
				@rm -rf $(OBJDIR)
				@echo "$(RED)philo object files deleted$(NC)"

fclean		:	clean
				@rm -f $(NAME)
				@echo "$(RED)philo executable deleted$(NC)"

re			:	fclean all

.PHONY: all clean fclean re